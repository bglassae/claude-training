# Claude Code Training + Context OS

This repo serves two purposes:
1. **Training course**: Run `/train` for an interactive walkthrough of Claude Code
2. **Your first Context OS**: During training, this repo transforms into your working knowledge system

## Training Instructor Mode

When running /train, you are an interactive Claude Code trainer. Follow the module structure exactly. Be encouraging but direct. Tailor every example to the trainee's specific work.

## Commands

| Command | Purpose |
|---------|---------|
| `/train` | Interactive training walkthrough (start here) |
| `/ingest` | Process raw content into structured knowledge nodes |
| `/graph-health` | Check the health of your knowledge graph |
| `/visualize` | Generate an interactive HTML visualization of your graph |

## Directory Structure

```
claude-code-training/
├── CLAUDE.md                    # This file -- navigation guide
├── .claude/
│   ├── commands/                # Slash commands (/train, /ingest, /graph-health, /visualize)
│   ├── agents/                  # Subagent definitions (ingestion-agent)
│   └── skills/                  # Your skills go here (created during training)
├── knowledge_base/              # Layer 1: Atomic knowledge nodes
│   ├── technical/               # Product/service knowledge
│   ├── business/                # Strategy, positioning, operations
│   ├── methodology/             # Frameworks, processes
│   └── emergent/                # New concepts not yet validated
├── 00_foundation/               # Layer 2: Operational documents
│   └── _synthesis/              # Summary documents
├── drafts/                      # Layer 3: Content you produce
├── templates/                   # Node and config templates
├── examples/                    # Training examples
├── raw_context/                 # Drop raw content here for processing
└── _system/
    └── knowledge_graph/         # Taxonomy, ontology, graph visualization
```

## Quality Standards

- Every knowledge node must have complete YAML frontmatter
- Tags should exist in `_system/knowledge_graph/taxonomy.yaml`
- Every node should link to 3+ related concepts via [[wiki-links]]
- Evidence attribution: [VERIFIED: source], [INFERRED: logic], [UNVERIFIABLE]
- New concepts start as 'emergent' status, promoted after 2+ citations

## How Knowledge Compounds

1. Feed raw content -> `/ingest` extracts structured nodes
2. Nodes link to each other via [[wiki-links]]
3. Skills read from the knowledge base to produce grounded output
4. New knowledge discovered during output gets fed back in
5. Run `/graph-health` to keep the system healthy
6. Run `/visualize` to see your knowledge graph grow

---

<!-- The section below gets populated during /train Module 1 -->

## Your Project

*This section will be filled in when you run /train.*
