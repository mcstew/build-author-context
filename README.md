# Build Author Context

`build-author-context` is an agent-facing skill for rapidly onboarding an author and making an AI agent ready to safely take on writing, editorial, publishing, marketing, and author-business tasks.

It creates and maintains a source-backed `author-context.md` organized around:

```text
Author -> Pen Name -> Series or Universe -> Project -> Current Task
```

The goal is not merely to collect comprehensive information. The goal is to make the agent useful for the author's highest-priority outsourced tasks as quickly as possible, while clearly identifying what it knows, what it inherits, what it may do, and where it still needs confirmation.

## Core Operating Ideas

```text
Outsourcing goals first.
Prefill before interviewing.
Lower tiers override inherited defaults.
Confirm before consequential action.
```

The skill first asks what the author wants to take off their plate in the next 30 to 90 days. It then gathers and structures the minimum context needed to perform those tasks competently, before expanding into broader onboarding.

## What This Repository Contains

- `SKILL.md` - the binding agent workflow.
- `references/context-schema.md` - the comprehensive coverage checklist, loaded as needed.
- `assets/author-context-template.md` - a reusable scaffold for new context files.
- `agents/openai.yaml` - optional UI metadata for OpenAI/Codex-style skill surfaces.

## What The Skill Produces

The expected primary output is:

```text
author-context.md
```

The file includes:

- a Quick Start and Context Router;
- current priorities and operating state;
- outsourcing-readiness assessment;
- agent permissions and approval boundaries;
- source ledger and confidence labels;
- hierarchical author, pen-name, series, and project records;
- explicit lower-tier overrides;
- source-of-truth pointers;
- open confirmations and context backlog;
- resume state and change history.

The context remains useful when incomplete. A focused version `0.1` that safely unlocks two important tasks is better than hundreds of blank fields.

## Hierarchy And Inheritance

Context flows downward:

1. Master author context contains universal information and defaults.
2. Pen-name context contains brand-specific identity, voice, audience, and boundaries.
3. Series context contains shared canon, world, positioning, and series conventions.
4. Project context contains book-specific intent, state, deadlines, and exceptions.
5. Current task instructions govern the immediate task but do not automatically become durable memory.

When instructions conflict, the more specific lower tier wins for the current task:

```text
Current Task > Project > Series > Pen Name > Author
```

Meaningful contradictions are recorded and surfaced for author confirmation rather than silently becoming permanent rules.

Lower-tier overrides may specialize creative or project defaults, but they may not silently weaken global privacy, confidentiality, identity-separation, approval, legal, financial, or `must never` rules.

## Rapid Onboarding Workflow

### 1. Establish The Readiness Target

The agent begins by asking:

> What do you most want this agent to take off your plate in the next 30 to 90 days?

The answer determines which context matters first. For example:

| Desired task | Priority context |
| --- | --- |
| Developmental editing | Pen-name style, series canon, project intent, feedback preferences |
| Newsletter drafting | Pen-name voice, audience, newsletter archive, promotion rules |
| Cover brief creation | Pen brand, series conventions, project positioning, visual references |
| Metadata optimization | Catalog source, positioning, formats, metadata philosophy, approvals |
| Launch support | Current project state, launch process, channels, vendors, permissions |

### 2. Gather A Small Seed Packet

The agent asks for:

- public author and pen names;
- highest-priority outsourced tasks;
- public links and relevant files;
- active projects;
- web-research permission;
- output location; and
- immediate privacy or action boundaries.

### 3. Prefill From Sources

The agent prioritizes author-provided files, existing context, official public pages, retailer listings, newsletters, interviews, and other relevant public sources.

It maps each useful fact to the highest applicable tier and avoids duplicating inherited information.

### 4. Build And Activate Version 0.1

The agent creates a focused first version using `assets/author-context-template.md`.

The comprehensive schema is treated as a coverage checklist. Fields are instantiated when they:

- support a desired outsourced task;
- reduce meaningful risk;
- have supporting evidence; or
- are explicitly requested.

Lower-priority unknowns go into a Context Backlog rather than becoming hundreds of blank fields.

### 5. Interview By Readiness Gap

The agent asks 3 to 7 questions at a time, beginning with gaps that block the author's desired tasks.

It explains what each question batch will unlock, converts casual answers into the correct hierarchy tier, and reads back significant interpretations for confirmation.

### 6. Verify And Hand Off

The skill does not stop when the Markdown file exists. The agent:

- assesses which tasks are ready now, ready with confirmation, or not ready;
- checks which hierarchy records and sources apply;
- verifies approval boundaries;
- optionally simulates one desired task without taking external action; and
- explains how the current or future agent should load the context.

A context file sitting on disk is not assumed to be active. The agent verifies how the current environment will retrieve it for relevant tasks before claiming onboarding is complete.

## Confidence And Provenance

Meaningful facts remain traceable:

```markdown
- S1: Official About page - https://example.com/about - accessed 2026-06-11 - authoritative public bio
- U1: Author statement in onboarding interview - 2026-06-11 - authoritative private preference

Primary genre: Cozy mystery. [SOURCE-CONFIRMED: S1]
Feedback preference: Direct notes with two alternatives. [AUTHOR-CONFIRMED: U1]
Brand promise: Warm found-family mystery. [INFERRED: S2, S4; needs confirmation]
```

Volatile facts such as deadlines and current priorities include review dates.

When sources conflict, the skill prefers the author's latest explicit confirmation, then author-approved source-of-truth files, then the newest authoritative public source, then other sources, and finally inference.

## Safety And Privacy

The skill never treats context as blanket permission to act.

It asks before publishing, contacting people, sending email, changing retailer metadata, changing accounts, spending money, revealing private pen-name links, or using sensitive information.

It never stores passwords, API keys, bank details, tax IDs, royalty credentials, or private contracts. Sensitive information is represented only through approved pointers and access rules.

## Installation

For Codex-style local skills:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/mcstew/build-author-context.git ~/.codex/skills/build-author-context
```

Then invoke it explicitly:

```text
Use $build-author-context. I want this agent ready to help with my next launch and weekly newsletter. Start from my website, retailer pages, and the files in this folder.
```

For an agent without a skills system, point it directly at `SKILL.md` and ask it to use the file as its operating procedure.

## Example Prompts

```text
Use $build-author-context to get ready to perform developmental edits on my current fantasy novel. Research my public pages and inspect the series bible in this folder before interviewing me.
```

```text
Use $build-author-context. I have 20 minutes. Build the smallest useful context that lets you draft my newsletter and organize my launch tasks safely.
```

```text
Resume my author context. Tell me which outsourced tasks you are ready to handle, then continue with the highest-value missing questions.
```

## Repository URL

GitHub: https://github.com/mcstew/build-author-context
