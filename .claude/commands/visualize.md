---
name: visualize
description: Generate an interactive HTML visualization of your knowledge graph
model: inherit
---

# Knowledge Graph Visualizer

Generate a self-contained HTML file that renders the knowledge graph as an interactive force-directed network diagram.

## Process

1. **Scan the knowledge base**

   Use Glob to find all .md files in knowledge_base/
   For each file, read and parse the YAML frontmatter to extract:
   - `name` (node label)
   - `domain` (for color coding)
   - `status` (emergent/validated/canonical)
   - `related_concepts` (for edges -- parse [[wiki-links]])
   - `tags` and `topics` (for hover info)

2. **Build the graph data**

   Create two arrays:
   - `nodes`: Each with id (filename without .md), label (name), domain, status, link_count
   - `links`: Each with source and target (from related_concepts wiki-links)

   For links, match [[wiki-link-name]] to actual filenames by normalizing both to lowercase-with-hyphens.

3. **Generate the HTML file**

   Write a self-contained HTML file to `_system/knowledge_graph/graph.html` that includes:

   - Inline D3.js (load from CDN: `https://d3js.org/d3.v7.min.js`)
   - A force-directed graph simulation
   - **Node colors by domain:**
     - technical = #3B82F6 (blue)
     - business = #10B981 (green)
     - methodology = #8B5CF6 (purple)
     - emergent = #F59E0B (amber)
   - **Node size** scaled by link count (more links = larger node)
   - **Node border** by status:
     - emergent = dashed
     - validated = solid thin
     - canonical = solid thick
   - **Edges** as lines connecting related concepts
   - **Hover tooltip** showing: name, domain, status, tags, topics
   - **Click** to highlight a node and its connections
   - **Legend** in the corner showing domain colors and status borders
   - **Title** at top: "Knowledge Graph -- [N] nodes, [M] connections"
   - Dark background (#1a1a2e) with light text for readability
   - Responsive -- fills the browser window

   The HTML must be fully self-contained (no external files except the D3 CDN).

4. **Open in browser**

   After writing the file, use Bash to open it:
   - macOS: `open _system/knowledge_graph/graph.html`
   - Linux: `xdg-open _system/knowledge_graph/graph.html`

5. **Report**

   "Your knowledge graph has been visualized:

   - [N] nodes across [domains]
   - [M] connections between concepts
   - [orphans] orphan nodes (no connections)

   File saved to: _system/knowledge_graph/graph.html
   
   Tip: As you ingest more content and add more nodes, run /visualize again to see your graph grow."

## Edge Cases

- If knowledge_base/ has no .md files (or only .gitkeep), generate a placeholder page that says "Your knowledge graph is empty. Run /ingest to add your first content, then /visualize again."
- If frontmatter can't be parsed for a file, skip it and note it in the report.
