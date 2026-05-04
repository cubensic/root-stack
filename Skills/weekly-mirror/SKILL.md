---
name: weekly-mirror
description: Weekly synthesis of journals and AI sessions into the vault. Updates me.md Current Focus, surfaces patterns and lessons, proposes people and broader vault updates — all for approval. Use when Ante says "run the weekly mirror", "do the mirror", "weekly review", "what happened this week", "run my digest", "update my patterns", or when a scheduled weekly task fires. Never apply vault changes without explicit approval.
---

# Weekly Mirror

*Weekly synthesis of Ante's journals and AI sessions into the vault. Covers identity updates (me.md, patterns, lessons) and broader vault housekeeping (people, strategy). Nothing gets written without approval.*

---

## When to run

- Ante says "run the weekly mirror", "do the mirror", "run my digest", "update my patterns", or similar
- The weekly-mirror scheduled task fires (Sunday 7am)
- Last run was more than 7 days ago → surface the suggestion at session start

---

## Step 0 — Harvest recent sessions

Before reading journals, pull in recent AI session context using the session management MCP tools:

1. Call `mcp__ccd_session_mgmt__list_sessions` to get the 15 most recent sessions
2. For each substantive session (skip sessions titled "Getting Started", "Initial greeting", or obvious one-liners), call `mcp__ccd_session_mgmt__search_session_transcripts` to read its content — use a broad query or the session ID to extract the key material
3. Focus on: decisions made, files changed, new projects or ideas surfaced, skills created or updated, things Ante approved or rejected, emotional signals

This session context step is often the richest source of signal — richer than journals — because it captures actual work output, not just reflection. No files are copied to the vault; sessions are read live.

---

## Step 1 — Read the journals

Read all journal files from the last 7 days:
- `Journal/Personal/` — personal daily entries (filenames: `DD-MM-YYYY [Day].md`)
- `Journal/Work/` — work daily entries (same naming)

Use Bash `ls` to list available files. Recent entries (current month) live directly in the folder root. Older entries may be in `Journal/Personal/2026/Month/` subfolders — check both locations if needed.

Note which days have no entry — gaps are signal too.

For pattern detection (monthly output), also read the last 30 days of entries. Keep the 7-day and 30-day sets mentally separate.

If no entries found from the last 7 days and no sessions found, stop and tell Ante: "No journal entries or session logs found from the last 7 days. Nothing to mirror."

---

## Step 2 — Read current vault state

Before proposing anything, read these files to understand what already exists:

- `me.md` — current identity snapshot and Current Focus section
- `About Ante/patterns/behavioral-patterns.md` — documented patterns (to avoid duplicates)
- `About Ante/patterns/lessons-learned.md` — existing lessons (to avoid duplicates)
- `About Ante/people.md` — people already documented (to know what's missing)

---

## Step 3 — Synthesize

Work through four output areas:

**A. Current Focus (weekly — always)**
What is Ante actually spending time on this week? What decisions or tensions are recurring? Produce 1–3 bullets. Each bullet is one line — crisp noun phrase or short sentence. Replace the existing section, don't append.

Example:
```
1. **YouTube B2C pivot** — 2 videos/week, building subscriber base as primary revenue engine
2. **Define and launch first B2C offer** — no product yet, Q2 deadline ($4k MRR by June 30)
3. **Japan trip planning** — May 2026, with Nick
```

**B. Behavioral patterns (monthly — only if 3+ evidence points)**
A pattern qualifies for `About Ante/patterns/behavioral-patterns.md` if:
- It appears in 3+ separate entries within the last 30 days
- It is not already documented
- It reveals something meaningful about how Ante operates

If it qualifies, draft a new entry in the same format as existing entries. If it doesn't hit the threshold, note it in the Signal Summary instead — don't force it.

**C. Lessons learned (weekly — only if a distinct lesson emerged)**
A lesson qualifies for `About Ante/patterns/lessons-learned.md` if:
- Ante explicitly stated a realization or conclusion in a journal or session
- It's not already captured
- It's specific enough to be actionable later

Format: `[YYYY-MM-DD] — [lesson in one crisp sentence]`

**D. People update (weekly — if new people appear or existing entries need updating)**
Check `About Ante/people.md`. Did new people appear 2+ times in journals/sessions? Did something notable happen with an existing person? Propose additions or updates.

**E. Broader vault proposals (weekly — up to 3 additional)**
What exists in the world now that isn't reflected in the vault?
- Decisions not yet in strategy docs
- Project pivots or new projects
- Goals/milestones that warrant a review note
- Content strategy shifts

Check `vault-map.md` to identify the right target files.

---

## Step 4 — Propose before writing

Present everything as a single structured proposal block. Use this format:

```
## 🪞 Weekly Mirror — [date range, e.g. Apr 13–19, 2026]

*[Automated / On-demand run. User present / not present.]*

### What I read
- Personal journals: [dates]
- Work journals: [dates]
- Sessions: [session titles]

---

### Signal Summary

**Headline:** [1–2 sentences — the most significant thing this week]

**Other signals:**
- [bullet per notable signal — max 6]

---

### Proposed Updates

**A. me.md Current Focus**
Replacing current section with:
1. [Priority 1]
2. [Priority 2]
3. [Priority 3]

---

**B. Behavioral Pattern — [name or "No new pattern"]**
[Draft entry using the existing format, or: "No new pattern — evidence below threshold (noted in signals above)."]

---

**C. Lesson Learned — [date or "No new lesson"]**
[Draft entry, or: "No distinct lesson extracted."]

---

**D. People — [summary or "No update needed"]**
[Proposed addition/update to people.md, or: "No new people or updates."]

---

**E. Other proposals (up to 3)**
[Proposal 1 — target file + exact content]
[Proposal 2 — ...]
[Proposal 3 — ...]
*(On-deck: [any overflow proposals noted briefly])*

---

Ready to apply? Reply "yes" to apply all, or tell me which parts to skip or change.
```

Stop here. Do not edit any vault files until Ante responds.

---

## Step 5 — Apply on approval

Ante can reply:
- `yes` or `apply all` — apply everything proposed
- `apply A, C, D` — apply specific sections
- `skip B` / `reject E2` — skip specific items
- Inline edits ("for C, change the wording to…")

Apply each approved change. Follow these rules without exception:

| File | Rule |
|---|---|
| `me.md` | Replace only the `## Current Focus` section. Update `*Updated: [month year]*`. Touch nothing else. |
| `About Ante/patterns/behavioral-patterns.md` | Append new entry at the bottom. Never edit existing entries. |
| `About Ante/patterns/lessons-learned.md` | Append new entry at the bottom. Never edit existing entries. |
| `About Ante/Goals/Reviews/` | Append only. Never edit past entries. |
| `About Ante/people.md` | Append new entries or update existing — never remove people. |
| `Knowledge Base/Raw/` | Immutable. Never touch. |
| `Journal/` | Read-only. Never edit entries after they are written. |

After applying, confirm:
```
✅ A — me.md Current Focus updated
✅ C — Lesson appended to lessons-learned.md
⏭ B — skipped (no qualifying pattern)
✅ D — people.md: added [name]
✅ E1 — [file]: [one-line description]
```

---

## Step 6 — Auto-memory

After vault changes, apply auto-memory entries for clear, non-debatable signals — new project decisions, finalized pivots, operational lessons, new named people (2+ appearances). Uncertain or sensitive entries go in the proposal instead.

---

## Step 7 — Log the run

After every run (automated or on-demand), append one entry to `Skills/weekly-mirror/weekly-mirror-log.md`. Do this regardless of whether changes were applied, rejected, or the run produced no output.

Entry format:

```
## [YYYY-MM-DD] weekly-mirror | [date range, e.g. Apr 22–28, 2026]
- Trigger: `automated` or `on-demand`
- Journals read: [e.g. "Personal: Apr 22, 24, 26 · Work: Apr 22, 23, 25" — or "none"]
- Sessions read: [count + brief titles, e.g. "3 — Weekly Planner, Lead Research, KB Ingest"]
- Applied: [e.g. "A, C, D" — or "pending approval" / "all rejected" / "no changes proposed"]
- Outcome: [1-sentence summary of what happened this week]
```

Append the entry at the bottom of the file. This is a write operation — do it unconditionally, without asking for approval.

---

## Guardrails

- Never overwrite existing patterns, lessons, or background entries — append only
- Current Focus is the only section of `me.md` that changes
- Maximum 3 bullets in Current Focus — if more than 3 things are active, pick the most urgent
- Patterns require 3+ evidence points across separate entries — not 3 mentions in one entry
- Don't propose things already in the vault — read before proposing
- Don't interpret emotions Ante hasn't explicitly named himself
- If Ante rejects a proposed change, don't retry the same item in the same session
