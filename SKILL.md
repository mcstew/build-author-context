---
name: build-author-profile
description: Build, enrich, and maintain a durable author operating profile for author AI agents. Use when an author wants to create an author context Markdown file, fill an indie-author workbook, onboard OpenClaw or another writing/editorial/publishing agent, gather public author data from websites, Amazon, retailer pages, newsletters, socials, interviews, or provided documents, prefill pen-name/series/project/business/agent-protocol context, or conduct a staged interview to complete missing author profile sections.
---

# Build Author Profile

## Outcome

Create or update a single Markdown "Author Operating Profile" that lets a capable agent collaborate with an author across creative work, editorial work, packaging, publishing operations, launch, vendor coordination, analytics, and catalog management.

The profile should be durable, source-backed, easy to resume, and useful even when incomplete. Prefer a strong partially filled profile with clear confidence labels over an intimidating blank workbook.

## Core Rules

- Prefill before interviewing. First gather useful public and user-provided context, then ask only for what remains unknown or needs confirmation.
- Do not invent. Mark uncertain content as tentative or inferred, and ask the author to confirm, revise, or reject it.
- Use public, accessible sources only unless the author provides private documents or explicit access.
- Do not collect or expose secrets. For passwords, tax records, contracts, dashboards, and private assets, record only the storage location or access rule the author approves.
- Keep source provenance. Every sourced fact should be traceable to a source label, provided file, explicit user statement, repeated behavior, or clearly labeled agent inference.
- Ask before publishing, contacting people, editing live retailer metadata, changing vendor accounts, spending money, sending email, revealing private pen-name links, or using sensitive data.
- Make pausing normal. If the author needs to stop, save the current profile plus a concise resume packet.

## Confidence Labels

Use these labels inline or in notes:

- `[CONFIRMED]` - directly confirmed by the author or an authoritative source.
- `[TENTATIVE]` - plausible but awaiting author confirmation.
- `[INFERRED]` - reasoned from available sources; explain the basis briefly.
- `[NEEDS AUTHOR]` - cannot be answered well without the author's input.
- `[PRIVATE POINTER ONLY]` - sensitive item should be referenced by location or access rule, not copied.
- `[N/A]` - intentionally not applicable.
- `[DEPRECATED]` - retained for history but no longer active.

## Workflow

### 1. Start or Resume

If an existing profile is available, read it first and preserve its structure, confirmations, and change history. If no profile exists, create `author-operating-profile.md` unless the user requests another name or the environment has no filesystem access.

Ask for a small seed packet before research:

- Public author name and any known pen names.
- Author website, Amazon Author Central link, retailer pages, Goodreads, BookBub, newsletter, social profiles, interviews, podcasts, press pages, or catalog pages.
- Any files or folders the author wants used, such as bios, style guides, series bibles, metadata sheets, launch plans, or backlist spreadsheets.
- Whether web research is allowed.
- Where the finished Markdown file should live.

If the author has no links, ask for the public name, genres, and book titles, then search if web access is available.

### 2. Gather and Prefill

Search or inspect sources in this priority order:

1. Author-provided files and links.
2. Author website and official bio pages.
3. Amazon Author Central, book pages, publisher pages, retailer listings, Goodreads, BookBub, LibraryThing, StoryGraph, Kobo, Apple Books, Barnes & Noble, Google Books.
4. Newsletter signup pages, reader magnets, Substack, Patreon, Kickstarter, Shopify/direct store, community pages.
5. Interviews, podcast pages, press kits, conference bios, guest posts, and social bios.
6. Public metadata, blurbs, series pages, cover/package cues, copyright pages, and back matter samples.

Extract only what is pertinent: names, bios, titles, series, genres, formats, release order, themes, audience cues, public positioning, links, recurring packaging, newsletter/social voice, and likely business posture. If a source blocks scraping, ask the author for a link, screenshot, export, or pasted text.

Maintain a Source Ledger with this format:

```markdown
- S1: Source title or file name - URL/path - accessed YYYY-MM-DD - notes on reliability
```

When adding facts to fields, cite briefly:

```markdown
Primary genres: Cozy mystery, paranormal mystery. [CONFIRMED: S2, S5]
Brand promise: Funny small-town mystery with a warm ensemble cast. [INFERRED: S3 blurbs, S4 reviews]
```

### 3. Build the Draft Profile

At the top of the profile include:

- Profile title.
- Record metadata.
- Resume State: last completed module, current open decisions, next recommended questions.
- Open Confirmations: short list of high-value items the author should approve.
- Source Ledger.
- Change Log.

Then create the profile using the schema below. Expand each schema item into its own `Field:` line. Duplicate repeatable records for each pen name, series/universe, and project.

Do not ask the author to fill every blank. Prefill what sources can support, mark gaps, and move through the highest-leverage modules first.

### 4. Interview in Stages

Ask 3 to 7 questions at a time. Use compact, human questions, not raw field dumps. Allow answers like "skip", "later", "unknown", or "use your draft".

For each stage:

1. Briefly state what you already found.
2. Ask the smallest number of questions needed to improve the profile.
3. Convert casual answers into structured fields.
4. Read back significant interpretations for confirmation.
5. Update Resume State and Change Log.

Preferred stage order:

1. Identity, sources, privacy, and public bios.
2. Career goals, priorities, constraints, success definition, and agent support boundaries.
3. Pen names and brand separation rules.
4. Series, universes, active projects, and canon sources.
5. Creative fingerprint, style, content boundaries, and revision preferences.
6. Process, tools, files, collaboration, and pause/resume habits.
7. Production, packaging, metadata, and distribution.
8. Marketing, audience, community, and metrics.
9. Business, legal, vendor, finance, and sensitive data rules.
10. Agent Protocol and Memory Rules.

### 5. Pause and Resume

When pausing, update or output:

```markdown
## Resume State
Last completed module:
Current module:
Next recommended questions:
Open confirmations:
Known source gaps:
Do not forget:
```

Never make the author repeat already captured answers. On resume, summarize what is known and continue from `Current module`.

### 6. Finish

When the profile is complete enough for use, deliver:

- The Markdown profile or the path where it was saved.
- A short summary of confirmed strengths and remaining gaps.
- The next best section to review later.
- Any high-risk assumptions requiring confirmation before an agent acts autonomously.

## Public-Source Prefill Map

- Website/about page: public bios, brand promise, pen names, newsletter, socials, community spaces, values, genre positioning.
- Amazon/retailer pages: titles, formats, series order, publication dates, categories, blurbs, packaging cues, comparable titles, pricing posture, exclusive/wide clues.
- Goodreads/BookBub/StoryGraph: series groupings, reader-facing genre expectations, review-volume signals, reader emotion cues, public author links.
- Newsletter/direct store: reader magnet strategy, direct-sales posture, newsletter voice, cadence clues, segmentation hints.
- Social profiles: voice, public AI stance, community norms, publicity comfort, platform priorities.
- Interviews/podcasts/press kits: mission, process, influences, goals, career model, constraints, values.
- Provided manuscript/style/canon docs: creative fingerprint, style rules, series continuity, content boundaries, revision workflow.
- Metadata spreadsheets/dashboards: catalog, identifiers, categories, keywords, pricing, formats, KPIs.

## Interview Prompts That Work

Use questions like these instead of dumping the schema:

- "I found these public bios. Which version feels most like you, and what should I change?"
- "Should I treat this pen name as publicly connected to your legal/primary author identity, private, or limited-cross-promo?"
- "For this brand, what should readers reliably feel after finishing one of your books?"
- "What should an assistant never do on your behalf without asking?"
- "Which current project matters most this quarter, and what would make it a success?"
- "When I disagree with a creative choice, should I challenge directly, offer alternatives, or mostly execute?"
- "Where should I point future agents for source-of-truth files without copying sensitive material into this profile?"

## Profile Schema

Use the exact section names below. Expand every item into an individual field line in the final profile.

### Master Profile

Fields: Record ID; Date created; Date last updated; Updated by; Status; Public author name; Legal name; Business entity name, if any; Imprint name, if any; Pronouns; Time zone; Primary country or jurisdiction; Preferred email; Preferred messaging channel; Preferred working hours; Do-not-disturb hours; Accessibility or communication accommodations; Short public bio; Medium public bio; Long public bio; Private mission statement; Long-term career goals; Current-year creative goals; Current-year business goals; How I define success; Risk tolerance; Preferred career model; Preferred balance between art, income, speed, and scale; Primary genres; Secondary genres; Primary audiences; Typical formats; Default rights posture; Default publishing posture; Default channel posture; Default outsourcing posture; Universal style notes that apply across all brands; Universal values I want reflected in my work; Universal content boundaries; Universal "do not generate" boundaries; Universal research standards; Universal quality bar; Universal AI-use policy; Universal AI-disclosure policy; Universal confidentiality policy; Current top priorities; Current biggest constraints; Support areas I most want from an agent; Support areas I do not want from an agent; Source-of-truth docs for the whole business; Where passwords or secrets live; Who may access what; Emergency contacts or backup operators.

### Pen Name Profile

Duplicate once per pen name.

Fields: Pen name; Public or private; Legal connection to master profile, if any; Genres and subgenres under this name; Target audience under this name; Age category or content band; Brand promise in one sentence; Brand promise in one paragraph; What readers expect emotionally from this name; What readers should never get from this name; Comparable titles or authors for this name; Signature themes and tropes; Themes and tropes to avoid; Heat, violence, profanity, and darkness norms; Voice adjectives; POV defaults; Tense defaults; Pacing defaults; Humor level; Language register; Narrative distance; Dialogue style notes; Recurring motifs or imagery; Things this brand is allergic to; Words, phrases, or visual cliches to avoid; Short bio for this pen name; Long bio for this pen name; Website; Newsletter; Primary socials; Reader community spaces; Cross-promotion allowed with other pen names; If limited, explain rules; Shared list, separate list, or mixed list; Shared street team or separate street team; Shared ARC pool or separate ARC pool; Shared vendors or dedicated vendors; Shared visual identity assets or separate assets; Public-facing AI stance for this name; Sensitivity or representation notes that matter for this brand; Current status of this pen name; Strategic goals for this pen name; Current projects under this pen name; Key opportunities or risks for this name.

### Series or Universe Profile

Duplicate once per series, universe, or nonfiction franchise.

Fields: Series or universe title; Associated pen name; Associated genre and subgenre; Core promise of the series; Series logline; Intended length or current roadmap; Published titles; Planned titles; Standalones connected to this universe; Reading order rules; Canon hierarchy if there are contradictions; Spoiler policy when discussing the series; Key themes; Required tonal qualities; Volume-to-volume continuity rules; Recurring worldbuilding rules; Character naming conventions; Place naming conventions; Glossary or pronunciation source; Relationship map source; Timeline source; Map or lore source; Forbidden retcons; Retcon policy if truly needed; Sensitive canon areas that need confirmation every time; Series-level content warnings or expectations; Series-level cover or packaging conventions; Series-level metadata conventions; Series-level back-matter conventions; Series-level launch expectations; Series-level rights or format restrictions; Source docs for canon.

### Project Profile

Duplicate once per active or published project.

Fields: Project ID; Working title; Public title, if different; Pen name; Series or universe; Project type; Current status; Business importance; One-sentence purpose of this project; Ideal reader for this project; Comparable titles; Formats planned; Target release window; Hard deadlines; Soft deadlines; Core concept or promise; Themes; Tropes; Reader emotions to target; Things this project must include; Things this project must not include; POV plan; Tense plan; Structure or beat model; Length target; Research requirements; Fact-check requirements; Sensitivity-read requirements; Canon dependencies; Risk areas or likely failure modes; Outline link; Draft link; Research folder; Character sheet location; Scene list location; Version naming convention; Backup location; Definition of ready for beta; Definition of ready for editor; Definition of ready for formatting; Definition of ready to ship; Editorial stage owner; Developmental editor, if any; Copyeditor, if any; Proofreader, if any; Beta readers, if any; Sensitivity readers, if any; Approval sequence before publication; Packaging notes; Cover direction notes; Blurb notes; Metadata notes; Keyword or category hypotheses; Launch notes; Promo hooks; Cross-sell links from this book to others; Format-specific needs for audio, print, large print, or direct sales editions; Post-release notes; Lessons learned; What the agent should remember next time.

### Creative Fingerprint and Style System

Fields: Three words that best describe my ideal writing; Three words that best describe what I want readers to say about my work; Three words that best describe what I never want my prose to feel like; Preferred POVs; POVs I use rarely or never; Preferred tenses; Preferred narrative distance; Preferred scene-to-summary ratio; Preferred exposition density; Preferred sentence length and rhythm; Preferred paragraph density; Preferred balance of internality, action, and dialogue; Preferred opening style; Preferred chapter ending style; Preferred level of explicitness in emotional beats; Preferred humor level; Preferred lyricism level; Preferred directness level; Preferred use of fragments, em dashes, italics, rhetorical questions, ellipses; Dialogue punctuation or styling preferences; Thought styling preferences; Swearing policy; Sex-scene policy; Violence depiction policy; Language or slur policy; Profanity ceiling; Content warning philosophy; Favorite craft strengths; Common weak spots; Bad habits I want caught; Words or constructions I often overuse; Words or constructions I dislike seeing in drafts; Favorite motifs or recurring images; Favorite emotional dynamics; Favorite character archetypes; Archetypes I avoid; Setting types I default to; Things I chronically underwrite; Things I chronically overwrite; Examples from my own work that are "gold standard"; Examples from my own work that are "do not repeat"; Outside influences I admire; Outside influences I do not want imitated directly; How to evaluate whether a passage "sounds like me".

### Process, Collaboration, and Revision Workflow

Fields: Idea capture system; Inbox or notes location for ideas; How I decide an idea is worth pursuing; Preferred concept-development method; Preferred outlining method; Beat sheet or planning framework, if any; Drafting cadence; Daily or weekly writing goal; Preferred sprint style; Ideal working session length; Best time of day for drafting; What tends to derail me; How an assistant can reduce friction during drafting; How I want brainstorming facilitated; How I want research presented; How I want feedback presented; How I want revision plans structured; Do I prefer margin notes, editorial letters, checklists, or conversation; How many options I want when given choices; Do I want an agent to challenge me, mirror me, or mostly execute; When to preserve ambiguity versus push for decisions; When to prioritize momentum versus precision; What "too much in the weeds" looks like to me; What "not detailed enough" looks like to me; Software used for drafting; Software used for revision; Software used for production; Storage locations; Folder conventions; File naming conventions; Versioning conventions; Backup conventions; Preferred export formats; Preferred comment formats; Meeting or check-in rhythm, if any.

### Production, Packaging, and Metadata Preferences

Fields: Default formats published; Default trim sizes; Default front matter preferences; Default back matter preferences; Copyright page preferences; Accessibility requirements; Alt text policy; Image-use policy; Interior design preferences; Typography preferences; House style sheet location; Style manual, if any; Formatting tool preference; Proofing expectations; Audio strategy; Audio narrator preferences; AI narration policy; Translation strategy; Large-print strategy; Special editions strategy; Cover philosophy in one sentence; Genre-cover conventions I want followed; Genre-cover conventions I want avoided; Approved visual references; Disallowed visual references; Blurb philosophy; Metadata philosophy; Keyword philosophy; Category philosophy; Series branding philosophy; A sample cover or product page that feels "right"; A sample cover or product page that feels "wrong".

### Distribution, Retail, and Channel Strategy

Fields: Primary platforms used; Secondary platforms used; Platforms intentionally not used; Exclusive or wide by default; If mixed, explain by format or series; Direct-sales strategy; Library strategy; Subscription strategy; Preorder philosophy; Pricing philosophy; Discounting philosophy; Territory strategy; Rights retained; Rights licensed or planned for licensing; Retailer-specific concerns or no-go rules; Metadata owner and approval authority; Launch sequence by format; Whether print is Amazon-only, wide POD, or offset-supported; Whether bookstore-friendly settings matter to this business; Whether special editions matter to this business; Default post-launch optimization process.

### Marketing, Audience, and Relationship Management

Fields: Primary reader segments; How I describe my reader community; Newsletter voice; Newsletter cadence; Newsletter goals; Reader magnet strategy; ARC strategy; Street team strategy; Review-asking strategy; How I want to talk about my books in public; How I do not want to talk about my books in public; Social platforms that matter; Platforms I am tired of or avoiding; Publicity comfort level; Podcasting or speaking comfort level; BookTok or short-form video comfort level; Paid ads strategy; Paid promos strategy; Event strategy; Community norms I want preserved; How to handle negative reviews; How to handle reader complaints; How to handle sensitive representation questions; How to respond if there is controversy around AI use, covers, narration, or marketing; Brand partnership rules; Cross-promo rules between pen names or peer authors; Metrics I care about most.

### Business, Legal, Vendor, and Finance Notes

Fields: Business entity status; Imprint status; Bookkeeping system; Where expense tracking lives; Tax calendar notes; Contract storage location; Rights tracker location; Permissions tracker location; Invoice approval process; Budget owner; Budget thresholds that require approval; Default payment terms for contractors; Default vendor categories used; Preferred vendors; Do-not-hire-again vendors; Vendor briefing format preference; Whether AI use by collaborators is allowed, restricted, or prohibited; Whether disclosure from collaborators is required; Legal topics that require professional review every time; Financial topics an agent may help organize but not decide; Royalty dashboard location; KPI dashboard location; Sensitive data handling rules.

### Agent Protocol and Memory Rules

Fields: Agent role in one sentence; Tasks the agent may do without asking; Tasks the agent may do after lightweight notice; Tasks the agent must always ask before doing; Tasks the agent must never do; Decisions the agent may recommend but not finalize; Decisions the agent may finalize if criteria are met; Criteria for autonomous action; Criteria for escalation; Preferred option format when presenting choices; Preferred level of context versus brevity; Preferred tone when disagreeing with me; Whether you should remind me of past preferences automatically; Whether you should challenge possible inconsistency across brands or projects; Whether you should proactively notice repeated patterns and propose durable memory; What counts as durable memory; What does not count as durable memory; How to record a newly learned preference; Whether new learnings require explicit confirmation; How to handle ambiguity; How to handle contradiction between old and new instructions; What confidence labels to use in memory; What provenance standards to use; What to do when a remembered preference harms the current task; How to phrase warnings or uncertainty; What to do if a project conflicts with pen-name rules; What to do if a task touches sensitive data; How often to summarize what has been learned about me; Preferred change-log format; Review cadence for this profile; Recent corrections I want remembered; Common wrong assumptions assistants make about me; Things I repeatedly have to explain that should become default knowledge; Green lights for collaboration; Red lines for collaboration.

### Source-of-Truth Library

Fields: Author website and primary bio source; Master spreadsheet for catalog or metadata; Series bible location; Character bible location; Research vault location; Cover assets location; Interior files location; Launch plan location; Marketing calendar location; Ad dashboard location; Newsletter archive location; Finance dashboard location; Rights and contracts location; FAQ or canned-response library; Glossary of house terms or shorthand; Archived decisions log.

## Manual Completion Strategy

If research comes up dry, continue with the staged interview. Start with these minimum viable questions:

1. "What name or pen names should this profile support, and which are public or private?"
2. "What do you most want an author agent to help with in the next 30 to 90 days?"
3. "What should an agent never do, generate, reveal, or decide without asking?"
4. "What are your active projects, and which one matters most right now?"
5. "Where are the source-of-truth files or notes future agents should consult?"

After those are answered, create a useful version 0.1 profile and keep filling the rest over time.
