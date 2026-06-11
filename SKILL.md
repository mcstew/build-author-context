---
name: build-author-context
description: Rapidly onboard an author and make an AI agent ready to safely outsource author-work tasks by building, enriching, activating, and maintaining a hierarchical, source-backed author context. Use when an author wants to create or resume author-context.md, onboard a writing/editorial/publishing/business agent, gather public or provided author data, map context across author, pen-name, series, and project tiers, define agent permissions, or assess whether an agent has enough context for specific outsourced tasks.
---

# Build Author Context

## Outcome

Make the current agent useful and trustworthy for the author's highest-priority outsourced tasks as quickly as possible.

Create or update a durable `author-context.md` that maps context through:

```text
Author -> Pen Name -> Series or Universe -> Project -> Current Task
```

The document must tell future agents:

- what context applies to a task;
- which lower-tier rules override inherited defaults;
- what sources are authoritative;
- what the agent can do autonomously;
- what remains unknown or requires approval; and
- which tasks the agent is ready to perform.

Prefer a useful, activated version `0.1` over an exhaustive blank workbook.

## Non-Negotiable Rules

- Ask what the author wants to outsource first. Prioritize context that unlocks those tasks.
- Prefill before interviewing. Gather useful public and user-provided context, then ask only high-value questions.
- Do not invent. Clearly label inference, uncertainty, and missing author input.
- Keep provenance. Every meaningful fact must trace to a source, author statement, repeated behavior, or labeled inference.
- Treat the schema as a coverage checklist, not a requirement to emit every blank field.
- Do not collect or expose secrets. Record only approved storage pointers or access rules.
- Ask before publishing, contacting people, sending email, editing live metadata, changing accounts, spending money, revealing private pen-name links, or using sensitive data.
- Keep pausing and resuming easy. Never make the author repeat captured answers.

## Context Hierarchy

### Inheritance

Context flows downward. A project inherits applicable series, pen-name, and author context unless a lower tier explicitly overrides it.

Resolve instructions in this order:

1. Current task instruction
2. Project context
3. Series or universe context
4. Pen-name context
5. Master author context

Task instructions govern the current task but do not become durable context unless the author confirms they should.

Lower-tier overrides may specialize creative, brand, process, or project defaults. They must not silently weaken global privacy, confidentiality, identity-separation, legal, financial, approval, or `must never` rules. Require explicit author confirmation before relaxing any such boundary.

Do not silently resolve meaningful contradictions. Follow the more specific rule for the immediate task only when it is safe and does not weaken a protected boundary. Record the conflict and ask the author to confirm the durable rule.

### Stable Records

Assign stable IDs that survive title and name changes:

```markdown
Record ID: author-primary
Pen ID: pen-romance
Series ID: series-moonfall
Project ID: project-moonfall-03
Parent records: pen-romance; series-moonfall
```

Use explicit parent links for every pen name, series, and project.

Use lowercase hyphenated IDs. Do not place legal names, private pen-name links, or other sensitive information in IDs.

### Durable Context Versus Current State

Keep these distinct:

- **Durable Context:** identity, brand rules, style, canon, process preferences, permissions.
- **Current Operating State:** active priorities, deadlines, project stages, launch plans, current vendors.
- **Open Decisions:** choices awaiting author input.
- **Context Backlog:** lower-priority coverage gaps.
- **Deprecated Context:** old rules retained with date and reason.

Add `Last reviewed` dates to volatile facts. Never present stale operating state as a permanent rule.

## Evidence And Confidence

Maintain a Source Ledger. Include author statements as sources when they establish durable context.

```markdown
- S1: Official About page - https://example.com/about - accessed 2026-06-11 - authoritative public bio
- U1: Author statement in onboarding interview - 2026-06-11 - authoritative private preference
```

Use compact labels:

- `[AUTHOR-CONFIRMED: U1]`
- `[SOURCE-CONFIRMED: S1]`
- `[INFERRED: S2, S4; needs confirmation]`
- `[TENTATIVE]`
- `[NEEDS AUTHOR]`
- `[PRIVATE POINTER ONLY]`
- `[N/A]`
- `[DEPRECATED: date and reason]`

For volatile facts, append `reviewed YYYY-MM-DD`.

An authoritative public source may confirm a publication date or public bio. It does not confirm private preferences, goals, or desired positioning.

When sources conflict, prefer:

1. the author's latest explicit confirmation;
2. an author-approved source-of-truth file;
3. the newest authoritative public source;
4. other public sources; then
5. agent inference.

Keep both values when the conflict matters, mark the older or rejected value appropriately, and ask rather than guessing.

## Workflow

### 1. Establish The Readiness Target

Before broad research or interviewing, ask:

> What do you most want this agent to take off your plate in the next 30 to 90 days?

Capture 1 to 5 desired outsourced tasks and rank them. For each task, identify:

- relevant pen name, series, and project;
- required source-of-truth files;
- permissions and approval boundaries;
- minimum context needed for competent execution; and
- the cost of getting it wrong.

Use this map to prioritize onboarding:

| Desired task | Prioritize first |
| --- | --- |
| Brainstorming or drafting | Pen-name voice, series rules, project goals, creative boundaries |
| Editing or revision | Creative fingerprint, project intent, canon, feedback preferences |
| Newsletter or social content | Pen-name brand, audience, archives, promotional boundaries |
| Cover or packaging brief | Pen name, series conventions, project positioning, visual references |
| Metadata or catalog work | Catalog source, positioning, categories, formats, approval rules |
| Launch or operations support | Current state, launch process, channels, vendors, permissions |
| General author assistance | Master context, active priorities, source library, agent protocol |

### 2. Start Or Resume

If an author context exists, read it first. Preserve stable IDs, confirmations, sources, deprecated history, and resume state.

If none exists, default to `author-context.md` at the author-approved location.

Ask for one compact seed packet:

- public author name and known pen names;
- top outsourcing goals;
- public links and relevant files or folders;
- active projects and the most important project now;
- whether public web research is allowed;
- where the finished context should live; and
- any immediate privacy or action boundaries.

If the author has no links, ask for public name, genres, and book titles, then search if allowed.

### 3. Gather And Prefill

Inspect sources in this order:

1. Author-provided files and links.
2. Existing context, instructions, style guides, canon documents, and project files.
3. Official website, bios, catalog, newsletter, and direct store.
4. Retailer, publisher, Goodreads, BookBub, StoryGraph, LibraryThing, and Google Books pages.
5. Interviews, podcasts, press kits, guest posts, and public social bios.
6. Public blurbs, metadata, packaging cues, copyright pages, and back matter samples.

Extract only pertinent facts. Do not scrape indiscriminately or copy substantial copyrighted text. If a source blocks access, ask for a screenshot, export, link, or pasted text.

Map every useful fact to the highest applicable tier:

- author-wide facts belong in Master Context;
- brand-specific facts belong under the pen name;
- shared canon and series conventions belong under the series;
- book-specific facts belong under the project.

Avoid duplicating inherited information. Record only lower-tier overrides or clarifications.

### 4. Build And Activate Version 0.1

Use [the output scaffold](assets/author-context-template.md) when creating a new file. Use [the comprehensive schema](references/context-schema.md) as a coverage checklist and read only the sections relevant to the readiness target.

Always include:

- Quick Start and Context Router;
- Current Operating State;
- Outsourcing Readiness;
- Agent Protocol and approval boundaries;
- Open Confirmations;
- Source Ledger;
- relevant hierarchy records with stable IDs and parent links;
- Context Backlog;
- Resume State; and
- Change Log.

Instantiate a schema field only when it is:

- supported by evidence;
- important to a desired outsourced task;
- necessary to prevent a costly, sensitive, or brand-damaging mistake; or
- explicitly requested by the author.

Put lower-priority unknowns in the Context Backlog instead of producing hundreds of `[NEEDS AUTHOR]` lines.

### 5. Interview By Readiness Gap

Ask 3 to 7 compact questions at a time. Start with gaps blocking desired tasks, then work down the hierarchy and through broader coverage.

For each batch:

1. State what is already known.
2. Explain what task the questions will unlock.
3. Ask the smallest useful set of questions.
4. Convert casual answers into the correct tier and fields.
5. Read back significant interpretations for confirmation.
6. Update readiness, resume state, and change log.

Allow answers such as `skip`, `later`, `unknown`, or `use your draft`.

After readiness-critical gaps, use this broader order:

1. Identity, privacy, business-critical facts, and source library.
2. Agent role, permissions, boundaries, and escalation rules.
3. Pen names and brand-separation rules.
4. Series, universes, projects, and canon.
5. Creative fingerprint, process, and revision preferences.
6. Production, packaging, metadata, and distribution.
7. Marketing, audience, community, and metrics.
8. Business, vendors, finance pointers, and legal boundaries.

### 6. Verify Readiness And Handoff

Do not finish at file creation. Prove the context is usable.

Create an `Outsourcing Readiness` assessment:

```markdown
Ready now:
- Draft newsletter options for pen-romance.

Ready with lightweight confirmation:
- Prepare a cover brief for project-moonfall-03.

Not ready:
- Perform a continuity edit on project-moonfall-03.
  Missing: authoritative timeline and canon hierarchy.

Always requires approval:
- Send newsletters; change retailer metadata; contact vendors.
```

Run a safe comprehension check against the context:

- Which hierarchy records apply to the highest-priority task?
- Which lower-tier rules override inherited defaults?
- What source is authoritative?
- What actions require approval?
- What important uncertainty remains?

When useful, simulate one desired task without taking external action. Ask the author whether the result feels sufficiently informed.

Explain where the file lives and how the current or future agent should load it. Ask before modifying always-loaded agent instructions or linking private context into another system.

A file sitting on disk is not activated by default. Verify the current agent can retrieve it for relevant tasks. Depending on the environment and the author's approval, activation may mean linking it from agent instructions, attaching it to a project, placing it in an auto-loaded context location, or explicitly loading it at task start.

### 7. Pause, Resume, And Maintain

Keep this packet current:

```markdown
## Resume State
Last completed onboarding stage:
Current readiness target:
Next recommended questions:
Open confirmations:
Known source gaps:
Do not forget:
```

On resume, summarize known context and continue from the readiness target. Update context when priorities, project stages, canon, brand rules, vendors, or permissions change.

Preserve source history, stable IDs, explicit overrides, corrections, and deprecated rules.

## Context Router Rules

Before performing an author-business task:

1. Read Agent Protocol, protected global boundaries, and Current Operating State.
2. Identify the relevant project, series, and pen name.
3. Load applicable context from author down to project.
4. Apply lower-tier overrides without weakening protected global boundaries.
5. Consult source-of-truth files when summaries are insufficient or stakes are high.
6. Check approval boundaries and unresolved confirmations.

Typical routes:

| Task | Context route |
| --- | --- |
| Newsletter | Master + Pen Name + Marketing + Current State |
| Draft or revision | Master + Pen Name + Series + Project + Creative Fingerprint |
| Cover brief | Pen Name + Series + Project + Packaging |
| Metadata | Pen Name + Series + Project + Distribution + catalog source |
| Launch task | Pen Name + Project + Distribution + Marketing + Current State |
| Vendor or financial organization | Master + Business Notes + Agent Protocol |

## Safety And Privacy

Never copy passwords, API keys, bank details, tax IDs, private contracts, royalty credentials, or unapproved hidden pen-name relationships into the context.

For sensitive material, record only an approved pointer and rule:

```markdown
Contract storage: Dropbox / Publishing / Contracts. Do not inspect or summarize without explicit approval. [PRIVATE POINTER ONLY]
```

Never treat the context as permission to publish, contact, spend, disclose, or make legal, tax, or financial decisions unless the author explicitly granted that authority and the current action meets its criteria.
