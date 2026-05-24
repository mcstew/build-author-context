# Build Author Profile

`build-author-profile` is an agent-facing skill for creating a durable author operating profile: a Markdown context file that helps an AI agent collaborate with an author across creative work, editorial work, publishing operations, packaging, launch, marketing, vendor coordination, analytics, and catalog management.

The point is not to hand an author a giant blank workbook and make them suffer through it. The point is to have an agent gather as much useful context as possible first, prefill the profile from public and provided sources, label uncertainty clearly, and then guide the author through only the remaining gaps in a staged, resumable interview.

## What This Repo Contains

- `SKILL.md` - the actual skill file. Point an agent at this file or install it into a compatible skill system.
- `agents/openai.yaml` - optional UI metadata for OpenAI/Codex-style skill surfaces.

This repo intentionally keeps the functional skill compact. The README explains how to use it, but `SKILL.md` is the source of truth for agent behavior.

## When An Agent Should Use This

Use this skill when the user asks for any of the following:

- Create an author context file.
- Build an author operating profile.
- Onboard an AI agent for writing, editing, publishing, or author-business support.
- Fill out an indie-author workbook or author profile.
- Gather author information from public sources and turn it into usable context.
- Create profiles for pen names, series, universes, projects, style, process, publishing operations, marketing, vendors, or agent permissions.
- Help an author define what an agent may do autonomously, what requires confirmation, and what is off limits.
- Resume a partially completed author profile interview.

Also use it when an author says something like:

```text
Help me make a context file so an AI agent understands my books and business.
```

```text
I want an assistant to know my pen names, style, projects, boundaries, and launch process.
```

```text
Can you scrape my public author info and build a profile I can edit?
```

## What The Skill Produces

The expected output is a Markdown file, usually named:

```text
author-operating-profile.md
```

That file is designed to become a durable working memory for author-facing agents. It includes:

- Record metadata and change history.
- A source ledger for public links, provided files, and author statements.
- A resume state so the author can pause and continue later.
- Open confirmations for anything that needs author approval.
- A Master Profile for the author/business.
- Repeatable Pen Name Profiles.
- Repeatable Series or Universe Profiles.
- Repeatable Project Profiles.
- Creative fingerprint and prose style preferences.
- Process, collaboration, and revision workflow preferences.
- Production, packaging, metadata, and distribution strategy.
- Marketing, audience, relationship, and community rules.
- Business, legal, vendor, and finance notes.
- Agent Protocol and Memory Rules.
- Source-of-truth library pointers.

The profile is useful even when incomplete. A good version 0.1 with source-backed facts, known gaps, and clear next questions is better than a perfect-looking file full of guesses.

## Core Operating Idea

The skill follows this principle:

```text
Prefill first. Interview second. Confirm always.
```

An agent should not immediately dump a long questionnaire on the author. It should first ask for a small seed packet, research or inspect the available sources, draft what it can, then ask the author targeted questions in small batches.

## Agent Quickstart

If you are an agent using this repo, do this:

1. Read `SKILL.md`.
2. Ask the user for the seed packet:
   - Public author name and pen names.
   - Website, Amazon Author Central, retailer pages, Goodreads, BookBub, newsletter, social links, interviews, press pages, or catalog pages.
   - Any files/folders to inspect, such as bios, series bibles, style sheets, metadata spreadsheets, launch plans, or backlist docs.
   - Whether web research is allowed.
   - Where the finished Markdown profile should live.
3. Gather public and provided context before asking deep questions.
4. Create or update `author-operating-profile.md`.
5. Add a Source Ledger.
6. Fill what can be supported.
7. Mark unknowns and assumptions with confidence labels.
8. Ask 3 to 7 author questions at a time.
9. Update Resume State after each stage.
10. Never store secrets. Use private pointers only.

## Installation

### Codex-style Skills

Clone or copy this repo into the skills directory your agent uses. For Codex-style local skills, that may look like:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/mcstew/build-author-profile.git ~/.codex/skills/build-author-profile
```

Then invoke it explicitly:

```text
Use $build-author-profile to create my author operating profile from my website, Amazon page, and provided notes.
```

### Any Agentic AI System

If your agent does not support skill folders, point it directly at `SKILL.md` and tell it:

```text
Use the instructions in this file as your operating procedure for building my author profile.
```

The skill is written to be self-contained enough for that mode. The agent should treat the profile schema and workflow inside `SKILL.md` as binding instructions.

## Expected Agent Workflow

### 1. Start Or Resume

If an existing profile exists, read it first. Preserve confirmed facts, prior source labels, open confirmations, and the resume state.

If no profile exists, create one. Default to `author-operating-profile.md` unless the user requests a different path.

### 2. Gather Sources

Prioritize sources in this order:

1. Author-provided files and links.
2. Author website and official bio pages.
3. Amazon Author Central, retailer pages, publisher pages, Goodreads, BookBub, StoryGraph, Kobo, Apple Books, Barnes & Noble, Google Books.
4. Newsletter pages, reader magnets, Substack, Patreon, Kickstarter, Shopify/direct store, community spaces.
5. Interviews, podcast pages, press kits, conference bios, guest posts, and public social bios.
6. Public metadata, blurbs, series pages, cover/package cues, copyright pages, and back matter samples.

The agent should extract only pertinent author-context information. It should not scrape indiscriminately or copy large copyrighted text into the profile.

### 3. Prefill The Profile

Use sources to prefill:

- Public bios.
- Pen names.
- Genres and audiences.
- Book titles and series.
- Release order and format clues.
- Public brand promise.
- Reader-facing emotional expectations.
- Public channels and communities.
- Newsletter/direct-sales clues.
- Packaging and metadata conventions.
- Public business posture, where supportable.

Do not invent private preferences. For example, do not infer a legal name, financial threshold, vendor rule, or hidden pen-name relationship unless the author explicitly confirms it.

### 4. Label Confidence And Provenance

Every meaningful fact should be traceable. Use the skill's confidence labels:

- `[CONFIRMED]`
- `[TENTATIVE]`
- `[INFERRED]`
- `[NEEDS AUTHOR]`
- `[PRIVATE POINTER ONLY]`
- `[N/A]`
- `[DEPRECATED]`

Use a Source Ledger entry like:

```markdown
- S1: Author website About page - https://example.com/about - accessed 2026-05-24 - official public bio source
```

Then cite compactly in fields:

```markdown
Primary genres: Cozy mystery, paranormal mystery. [CONFIRMED: S1, S4]
Brand promise: Warm, funny small-town mystery with a found-family ensemble. [INFERRED: S2 blurbs, S5 series page]
```

### 5. Interview In Small Batches

Ask 3 to 7 questions at a time. Avoid pasting the whole schema as a questionnaire.

Good agent behavior:

```text
I found two public bios and seven books across two series. Before I draft the pen-name section, can you confirm:
1. Should this pen name be treated as public, private, or limited-cross-promo?
2. What should readers reliably feel after finishing one of these books?
3. Are there themes, tropes, or content boundaries this brand should avoid?
```

Bad agent behavior:

```text
Please fill in these 250 fields.
```

### 6. Preserve Pause And Resume State

Authors may need to stop. The agent must keep a resume packet:

```markdown
## Resume State
Last completed module:
Current module:
Next recommended questions:
Open confirmations:
Known source gaps:
Do not forget:
```

On resume, summarize what is already known and continue from the current module. Do not ask the author to repeat answers already captured.

## Safety And Privacy Rules

This skill is designed for author-business context, which can include sensitive information. Agents must be conservative.

Never copy secrets into the profile:

- Passwords.
- API keys.
- Bank details.
- Tax IDs.
- Private contracts.
- Royalty dashboard credentials.
- Private legal documents.
- Hidden pen-name relationships unless explicitly approved.

For sensitive information, record only pointers or access rules:

```markdown
Where passwords or secrets live: 1Password vault, author access only. [PRIVATE POINTER ONLY]
Contract storage location: Dropbox / Publishing / Contracts. Do not summarize contract terms without explicit approval. [PRIVATE POINTER ONLY]
```

Ask before:

- Publishing anything.
- Contacting vendors, readers, reviewers, or collaborators.
- Editing live retailer metadata.
- Changing accounts or platform settings.
- Spending money.
- Sending email.
- Revealing private pen-name links.
- Making legal, tax, or financial decisions.

## What Makes A Good Finished Profile

A good profile should be:

- Source-backed.
- Easy for another agent to scan.
- Honest about uncertainty.
- Practical for ongoing author work.
- Respectful of pen-name boundaries.
- Clear about permissions and autonomy.
- Useful even if only partially complete.
- Designed to evolve.

The profile should help an agent answer:

- Who is this author?
- What do they write?
- Who do they write for?
- What should their work feel like?
- What should their work never feel like?
- What projects matter right now?
- What are the source-of-truth files?
- What can the agent do without asking?
- What must the agent always ask before doing?
- How should the agent remember new preferences?

## Minimum Viable Profile

If public research comes up dry, the agent should still create a useful version 0.1 by asking:

1. What name or pen names should this profile support, and which are public or private?
2. What do you most want an author agent to help with in the next 30 to 90 days?
3. What should an agent never do, generate, reveal, or decide without asking?
4. What are your active projects, and which one matters most right now?
5. Where are the source-of-truth files or notes future agents should consult?

Then create the first profile and continue filling it over time.

## Example User Prompts

```text
Use $build-author-profile. My author name is Jane Example. Start from janeexample.com, my Amazon Author Central profile, and the metadata spreadsheet in this folder. Build a profile I can review.
```

```text
Use this skill to create an author context file for my romance pen name. Please research my public pages first, then ask me for anything private or uncertain.
```

```text
Resume my author operating profile. Read the existing Markdown file, summarize what is already confirmed, and continue with the next unanswered section.
```

```text
Build the smallest useful author profile today. I only have 20 minutes, so ask the minimum questions needed to make a version 0.1.
```

## Maintaining The Profile

Treat the profile as a living document. Update it when:

- A new pen name is added.
- A series changes direction.
- A project moves stages.
- The author changes their process or boundaries.
- A vendor is added or removed.
- The author confirms or rejects an inferred preference.
- A launch, release, or postmortem creates durable lessons.
- Agent permissions change.

When updating, preserve:

- Change Log.
- Source Ledger.
- Deprecated facts when they explain current rules.
- Confidence labels.
- Open confirmations.

## Repository URL

GitHub: https://github.com/mcstew/build-author-profile
