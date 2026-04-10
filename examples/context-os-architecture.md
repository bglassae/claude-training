# Context OS Architecture -- The Patterns That Make It Compound

A Context OS is a structured knowledge system where AI gets smarter over time. Here's how the architecture works and why each piece matters.

## The Three Layers

```
Layer 1: Atomic Knowledge (knowledge_base/)
  Individual facts, insights, frameworks -- each a separate file with
  structured frontmatter, evidence tags, and wiki-links to related concepts.
  Organized by domain: technical/, business/, methodology/, emergent/

Layer 2: Operational Docs (00_foundation/)
  Strategic documents that compose Layer 1 concepts -- positioning,
  messaging, personas, synthesis docs. These reference atomic concepts
  via [[wiki-links]] but never redefine them.

Layer 3: Outputs (drafts/)
  Content you produce, grounded in Layers 1 and 2. Each output links
  back to the knowledge nodes that informed it via source_nodes in
  its frontmatter. This creates traceability -- you can always see
  what knowledge backed a particular output.
```

## Five Key Patterns

### 1. CLAUDE.md as Navigation Guide

CLAUDE.md is the first thing Claude reads in every session. It tells Claude:
- What this project is and what it's for
- Where to find things (directory structure)
- What rules to follow (quality standards, writing style)
- How to use tools and integrations

The more you refine CLAUDE.md, the smarter every session starts. When Claude does something wrong, update CLAUDE.md so it never happens again. Over time, it becomes a comprehensive guide to your project that any AI session can use instantly.

### 2. Ingestion as the Flywheel

Raw content goes in. Structured knowledge comes out.

```
Raw content (transcript, document, notes)
  -> /ingest command
    -> Extracts atomic concepts
    -> Creates structured nodes with frontmatter
    -> Links to existing nodes via [[wiki-links]]
    -> Saves to knowledge_base/ with correct domain folder
```

You don't manually create knowledge nodes. You feed content to an ingestion pipeline and it does the extraction. This is the flywheel -- every piece of content you process adds to the knowledge graph, and every skill you run gets better because there's more knowledge to draw from.

### 3. Status Lifecycle

Not all knowledge is equal. New concepts start as "emergent" -- unproven. They live in `knowledge_base/emergent/` until they prove themselves.

```
emergent  -- First appeared, single source
  -> validated  -- Confirmed by 2+ independent sources
    -> canonical  -- Core concept, widely referenced
```

This prevents premature generalization. A single mention in one meeting doesn't become a foundational concept. What survives across multiple sources is what's real.

### 4. Evidence Attribution

Every claim in the knowledge base gets tagged:

- **[VERIFIED: source:line]** -- Direct evidence exists. You can point to the exact source.
- **[INFERRED: from X + Y]** -- Deduced by combining multiple pieces of evidence. The logic is stated.
- **[UNVERIFIABLE]** -- Cannot be confirmed. The claim exists but there's no way to check it.

This keeps the AI honest. When a skill pulls from the knowledge base to write a proposal or a report, it knows what it actually knows vs. what it's guessing. No more confident-sounding hallucinations.

### 5. Skills Read the KB

This is where everything connects. Skills don't work in isolation -- they read from the knowledge base.

A skill that writes a sales proposal:
- Pulls real customer quotes from prospect language nodes
- Uses competitive data from competitive landscape nodes
- References case studies from case study nodes
- Applies messaging frameworks from operational docs

The more knowledge you ingest, the better every skill performs. This is the compounding effect: knowledge in, better outputs out, new knowledge discovered in the process, fed back in.

## The Compounding Cycle

```
1. Ingest raw content (transcripts, docs, notes)
2. Knowledge graph grows (more nodes, more links)
3. Skills draw from richer knowledge
4. Outputs are more grounded and accurate
5. New knowledge discovered during output creation
6. Feed it back in (go to step 1)
```

After a few weeks of this cycle, the AI knows more about your domain than you could ever fit in a single prompt. That's the power of a Context OS -- it's not a chatbot you explain things to every time. It's a system that already knows.

## Getting Started

The quickstart (https://github.com/jacob-dietle/gtm-context-os-quickstart) sets up this entire architecture in 10 minutes. It creates the directory structure, CLAUDE.md, and ingestion pipeline. Your job from there: feed it content, build skills, produce grounded output. Repeat.
