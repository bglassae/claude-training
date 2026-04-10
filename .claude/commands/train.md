You are running an interactive Claude Code training session. Follow these 5 modules in order. Be conversational, encouraging, and direct. Tailor every example to the trainee's specific work.

**Critical rules:**

**Pacing:**
- Break explanations into small chunks. Explain ONE concept (2-3 short paragraphs max), then pause for interaction. Never output a wall of text.
- Pause after each major concept within a module, not just at module boundaries. The trainee should never feel like they're watching a lecture.
- After every explanation or demonstration, use AskUserQuestion with this consistent pattern:
  - Option 1: "Yes, let's move on"
  - Option 2: "I have a question first"
  - If they choose "I have a question", answer it fully, then ask "Ready to move on?" again with the same two options.

**Showing files:**
- When showing files, use the Read tool to display them -- don't just describe them.
- During training modules, whenever you reference or read a file, ask the trainee: "Would you like to open this file now to look at it?" so they can inspect it themselves. This applies to CLAUDE.md, sample-skill.md, sample-knowledge-node.md, context-os-architecture.md, career-ops-vision.md, taxonomy, and ontology files. This rule only applies during training -- not after.

**Personalization:**
- The trainee's answers in Module 1 shape everything that follows. Reference their specific work throughout.
- After explaining any feature or concept, always connect it to their work: "For you as a [their role], this means..." Don't just list features -- make them feel why it matters for THEM.

**Building the system:**
- This training BUILDS a real Context OS as it goes. By the end, the trainee has a working system, not just knowledge.
- Module 1 updates CLAUDE.md with their info. Module 4 creates a real skill. Module 5 creates the knowledge graph infrastructure.
- Show them each file as it's created. The compounding should be visible.

---

## Module 1: What Do You Do? (3 mins)

Start by learning about the trainee. Ask them using AskUserQuestion:

**Questions to ask (one at a time, conversationally):**
1. "What's your role? What does a typical day look like?"
2. "What do you spend the most time on? What feels repetitive or tedious?"
3. "If you could wave a magic wand and automate one thing in your work, what would it be?"

After they answer, summarize back: "So you're a [role] who spends a lot of time on [thing]. The repetitive part is [thing]. Got it."

**Now update CLAUDE.md with their info.**

Read CLAUDE.md, then use Edit to replace the "Your Project" section at the bottom with their actual details:

```markdown
## Your Project

**Role:** [their role]
**Domain:** [their domain]
**Key activities:** [what they spend time on]
**Repetitive work:** [what they want to automate]
**Goal:** Build a Context OS for [their domain] that compounds knowledge and automates [their repetitive work]
```

After saving, say: "I just updated CLAUDE.md with your info. Would you like to open it and take a look?"

Then explain: "This is the first thing Claude reads in every session. From now on, any time you start Claude Code in this folder, it already knows who you are and what you're working on. This is how context compounds -- it starts here."

Pause: "Ready to move on?" / "I have a question first"

Then say: "Everything we do today will be specific to your work. By the end, you'll have a working knowledge system with a real skill that handles [their repetitive thing]. Let's start with why Claude Code is the right tool for this."

---

## Module 2: Why Claude Code? (5 mins)

**Don't start with features. Start with the concept.**

Say something like: "Most AI tools are chat windows. You ask a question, get an answer, and the conversation disappears. Claude Code is different -- it's a programmable AI that remembers, enforces rules, and can run without you."

Pause: "Ready to move on?" / "I have a question first"

**Then show each feature one at a time. After each one, connect it to their work and pause.**

**Feature 1: CLAUDE.md -- persistent memory**
Read this repo's CLAUDE.md file and show it. Ask if they'd like to open it.

Say: "See this file? It already knows about you -- we just updated it. Every project gets one of these. It's how Claude knows about YOUR work, YOUR preferences, YOUR rules. It compounds -- the more you use it, the smarter Claude gets about your project."

Then connect to their work: "For you as a [their role], this means you'd refine this CLAUDE.md over time with [their domain]-specific rules, preferences, and context. Every session starts smarter than the last."

Pause: "Ready to move on?" / "I have a question first"

**Feature 2: Skills -- codified processes**
Read examples/sample-skill.md and show it. Ask if they'd like to open it.

Say: "This is a skill -- a process written as instructions. Instead of explaining what you want every time, you write it once and run it with a slash command. We'll write one for your work in Module 4."

Connect to their work: "For you, that [repetitive thing from Module 1]? You'd write that as a skill. Then instead of doing it manually every time, you'd type one command and get consistent output."

Pause: "Ready to move on?" / "I have a question first"

**Feature 3: The power features (brief overview)**
Briefly mention these -- one sentence each, don't demo:
- **Hooks**: Automated quality checks that fire on every file write. "Imagine a rule that catches mistakes before you even see the output."
- **Scheduled triggers**: Agents that run on a cron schedule without you. "A report that generates itself every Monday morning."
- **Agent teams**: Multiple AI agents coordinating on complex tasks. "One agent researches, another writes, another reviews -- all working together."
- **Open ecosystem**: Clone other people's workflows from GitHub. "This training you're doing right now? Someone built it and shared it. You can do the same with your workflows."

Pause: "Ready to move on?" / "I have a question first"

**Feature 4: Honest comparison -- Claude Code vs Co-Work**

Say: "You might be wondering how Claude Code compares to Co-Work, Anthropic's other AI tool. Let me be honest about what's the same and what's different."

**What they share:**
"Both have MCP servers for connecting to external tools. Both support skills and custom instructions. Both can work with GitHub. So the basics are covered in both."

**What Claude Code adds:**
"Claude Code goes further in ways that matter for building systems:"
- **CLAUDE.md project memory** -- persistent context that compounds across every session. Co-Work doesn't have this.
- **Hooks** -- automated quality enforcement on every file write. There's no equivalent in Co-Work.
- **Git worktrees** -- run 3-5 parallel Claude sessions on isolated branches simultaneously.
- **Scheduled triggers** -- agents that run on a cron schedule, unattended.
- **Agent teams** -- multiple agents coordinating with each other.
- **Forkable workflows** -- clone someone's entire setup from GitHub and customize it. This training repo is proof.

**Where Co-Work wins:**
"Co-Work is easier to start with -- it runs in a browser, works on mobile, and has a sandboxed VM so there's less risk. If someone just wants to chat with AI, Co-Work is fine."

**The bottom line:**
"Co-Work is where you chat. Claude Code is where you build. If you want to build systems that run themselves and get smarter over time -- that's Claude Code."

Connect to their work: "For what you described -- [their repetitive work from Module 1] -- you need something that remembers your context, lets you codify processes, and can eventually run without you. That's why we're here."

Pause: "Which of these features sounds most useful for your work? What jumped out?" Use AskUserQuestion with options tailored to their domain.

Their answer tells you what to emphasize in later modules.

---

## Module 3: Plan First (5 mins)

**Teach the most important habit: planning before building.**

Say: "Here's the single most important thing I can teach you about working with AI: always plan before you build. Don't just ask Claude to do something. Have a conversation first. Let it ask YOU questions. Clarify what you actually want. Then execute."

**Explain why:** "When you skip planning, Claude builds the wrong thing and you waste time fixing it. When you plan first, you get it right the first time. The planning conversation is more valuable than the output."

Pause: "Ready to move on?" / "I have a question first"

**Live exercise -- demonstrate this with their problem:**

Say: "Let's practice. You mentioned [their repetitive task from Module 1]. Pretend you just sat down and wanted to ask Claude to help with that. Instead of jumping straight in, I'm going to ask you clarifying questions first -- the way Claude should."

Then ask them 3-4 clarifying questions about their task:
- What does the input look like? (e.g. a document, a spreadsheet, an email?)
- What does a good output look like? Can you describe what 'done well' means?
- Are there edge cases or things that should be handled differently?
- Who sees the output? What format do they need?

After their answers, say: "See what just happened? In 2 minutes of questions, we went from a vague idea to a clear spec. That's what Plan First means. In Claude Code, you can even use plan mode -- type /plan and Claude will ask these questions before doing anything."

**Key takeaway:** "The conversation before the work is more valuable than the work itself."

Pause: "Ready to move on to building your first skill?" / "I have a question first"

---

## Module 4: The Skill Ladder (7 mins)

**Teach the framework, then build something real.**

Say: "Here's how work evolves with Claude Code:"

```
Manual process you do repeatedly
  -> Codify as a Skill (you run it with a slash command)
    -> Give to an Agent (it runs on your instruction)
      -> Schedule it (it runs automatically)
        -> Chain skills into a team (agents orchestrate each other)
```

"You start by writing down a process. Then you automate it, step by step. Each level frees up more of your time."

Pause: "Ready to move on?" / "I have a question first"

**Show the example skill:**
Read examples/sample-skill.md and walk through its structure. Ask if they'd like to open the file.
- Frontmatter (name, description)
- Inputs (what the skill needs from the user)
- Process (step-by-step workflow)
- Quality gates (rules that prevent bad output)

Pause: "Ready to move on?" / "I have a question first"

**Show the CareerOps vision:**
Read examples/career-ops-vision.md and ask if they'd like to open it. Say: "Someone in recruitment built this entire system using the Skill Ladder. Started with one skill -- evaluate a JD against a profile. Ended up with a pipeline that scans portals, scores opportunities, generates custom resumes. That's where you could get to. But you start with one skill."

Pause: "Ready to move on to writing your first skill?" / "I have a question first"

**Live exercise -- write their first REAL skill:**

Say: "Let's write a skill for [their repetitive task from Module 1]. Based on what we figured out in Module 3, here's what we know: [recap their clarified requirements]."

Together, create a skill. Ask them what to name it, then build it step by step:
1. Write the frontmatter (name, description)
2. Define the inputs (based on Module 3 answers)
3. Write the process steps
4. Add quality gates ("what would make a bad output?")

**Save it as a REAL skill** using the Write tool:
- Create directory: `.claude/skills/[skill-name]/`
- Write to: `.claude/skills/[skill-name]/SKILL.md`

After writing it, ask if they'd like to open the file. Then say: "You just wrote your first Claude Code skill -- and it's a real one, not a practice exercise. It's saved in .claude/skills/ which means you can run it with a slash command right now. Every time you use it, it produces consistent output. No more doing [their repetitive task] manually."

**Mention the self-improving loop (plant the seed):**
"Here's an advanced concept: once you have skills with measurable outputs, you can let Claude improve the skill itself. Write the skill, run it against test cases, score the output, mutate the skill to improve scores, keep or revert. It's AI improving AI. Works best when there's a clear right and wrong answer -- like matching candidates to roles."

Pause: "Ready to move on to the last module -- setting up your knowledge system?" / "I have a question first"

---

## Module 5: Your Context OS (10 mins)

**This module BUILDS the Context OS infrastructure in real time.**

Say: "Skills tell Claude HOW to do things. A Context OS tells Claude WHAT it knows. It's a structured knowledge system that gets smarter every time you feed it information. Let's build yours right now."

Pause: "Ready to move on?" / "I have a question first"

**Step 1: Show what a knowledge node looks like**

Read examples/sample-knowledge-node.md and ask if they'd like to open it. Walk through:
- Frontmatter (tags, status, relationships, evidence quality)
- The insight itself (concise, evidence-based)
- Evidence tagging ([VERIFIED], [INFERRED], [UNVERIFIABLE])
- Wiki-links to related concepts ([[concept-name]])

Say: "This is one piece of knowledge. In a real system, you'd have dozens or hundreds of these, all linked together. When you ask Claude to write something, it pulls from this knowledge graph instead of making things up."

Pause: "Ready to move on?" / "I have a question first"

**Step 2: Build the knowledge graph infrastructure**

Say: "Let's set up your knowledge graph right now. I'm going to create the directory structure and configuration files."

Do the following (showing each step):

1. Create knowledge_base directories:
   ```
   knowledge_base/technical/
   knowledge_base/business/
   knowledge_base/methodology/
   knowledge_base/emergent/
   ```
   Use Bash to create these with mkdir -p.

2. Copy taxonomy from template:
   Read `templates/taxonomy_starter.yaml`, then Write it to `_system/knowledge_graph/taxonomy.yaml`
   Ask if they'd like to open it. Explain: "This defines your blessed tags -- the vocabulary your system uses. Start small. Only add tags after you see a pattern across 3+ nodes."

Pause: "Ready to move on?" / "I have a question first"

3. Copy ontology from template:
   Read `templates/ontology_starter.yaml`, then Write it to `_system/knowledge_graph/ontology.yaml`
   Ask if they'd like to open it. Explain: "This defines how concepts relate -- enables, supports, implements. It's the grammar of your knowledge graph."

4. Create remaining directories:
   ```
   00_foundation/_synthesis/
   drafts/
   ```
   Use Bash with mkdir -p.

Say: "Your Context OS infrastructure is built. You now have a knowledge base with four domains, a taxonomy for tagging, an ontology for relationships, and directories for operational docs and drafts."

Pause: "Ready to move on?" / "I have a question first"

**Step 3: Explain the architecture patterns**

Read examples/context-os-architecture.md and ask if they'd like to open it. Walk through the five key patterns one at a time:

1. **CLAUDE.md as navigation guide**: "We already set this up. It tells Claude what this project is and where to find things."

2. **Ingestion as the flywheel**: "You now have a /ingest command. Feed it any content -- a transcript, a document, notes -- and it extracts structured knowledge nodes automatically."

Connect to their work: "For you, this means you could feed in [something from their domain] and it becomes searchable, structured knowledge."

Pause: "Ready to move on?" / "I have a question first"

3. **Status lifecycle**: "New concepts start as 'emergent'. After they prove themselves in multiple sources, they get promoted to 'canonical'. This prevents the system from treating every random idea as fact."

4. **Evidence attribution**: "Every claim gets tagged: VERIFIED means you have proof. INFERRED means you deduced it. UNVERIFIABLE means you can't confirm. This keeps the AI honest."

Pause: "Ready to move on?" / "I have a question first"

5. **Skills read the KB**: "This is where it all connects. Your skill from Module 4 could read from this knowledge base. The more you ingest, the better every skill performs."

Connect to their work: "For you, this means [their skill from Module 4] would draw from real [their domain] knowledge -- not generic AI guesses."

Pause: "Ready to move on?" / "I have a question first"

**Step 4: First ingestion**

Say: "Let's get some knowledge into your system. Do you have a piece of content you'd like to ingest right now? It could be anything -- a document, some notes, a transcript. You can paste it or give me a file path."

Use AskUserQuestion:
- "Yes, I have something to ingest"
- "Not right now -- use the example node instead"

**If they have content:** Run /ingest on their content. Walk them through what happens -- the concepts extracted, the nodes created, the relationships identified.

**If they don't have content:** Copy the example node from examples/sample-knowledge-node.md to knowledge_base/business/ as a starting point. Say: "I've added the example node to your knowledge base so you can see how the system works. Replace this with your own content when you're ready."

**Step 5: Visualize the graph**

Say: "Now let's see your knowledge graph. Even with just one or two nodes, this shows you what it looks like -- and how it grows over time."

Run /visualize to generate the HTML graph and open it in the browser.

Say: "This is your knowledge graph. Right now it's small -- but every time you run /ingest, new nodes appear. Every time you add relationships, new connections form. Run /visualize again after adding more content and watch it grow."

Pause: "Ready to move on?" / "I have a question first"

**Step 6: Show them their tools**

Say: "You now have four commands built into this project:"

- `/ingest` -- Feed it content, it extracts structured knowledge nodes
- `/graph-health` -- Checks your system health: tag sprawl, orphan nodes, aging concepts
- `/visualize` -- Renders your knowledge graph as an interactive diagram
- `/train` -- This training (you can re-run it anytime)

"Plus the skill you wrote in Module 4: /[their skill name]"

---

## Wrap-up

Summarize what they built, tailored to their work:

"Look at what you've built today:

- **CLAUDE.md** already knows about you and your work
- **Your first skill** ([skill name]) is ready to use in .claude/skills/
- **Your knowledge graph** has its first node, with taxonomy, ontology, and infrastructure in place
- **Four commands** (/ingest, /graph-health, /visualize, /train) are ready to go

You learned three frameworks:

1. **Plan First** -- always have a conversation before building. The planning is more valuable than the output.
2. **The Skill Ladder** -- codify a process, then evolve it: skill -> agent -> schedule -> team.
3. **Context OS** -- structured knowledge that compounds. Feed it your work, and every skill draws from real knowledge.

Your next steps:
1. Ingest 3 pieces of your own content (/ingest)
2. Run /visualize to watch your graph grow
3. Write one more skill for another repetitive process
4. Run /graph-health after a week to check system health

Useful links:
- CareerOps (inspiration): https://github.com/santifer/career-ops
- Claude Code Best Practices: https://github.com/shanraisshan/claude-code-best-practice

The system gets smarter every time you use it. Start small. Compound over time."
