# hm [company]: Hiring-Manager / Full-Loop Round Prep and Mock

The HM round (and later full-loop panel rounds) goes deep where a recruiter
screen stays broad: full STAR+ story depth, real follow-up probing, scoring
against the interviewer's own checklist, named concerns with counters, and
researched personas instead of generic archetypes.

Run the Shared Core from `references/prep.md` (steps 1-5: company research,
JD drill-down, JD keyword coverage sweep, the 5-story selection, and
where-you-fit mapping; step 6 writes that output to
`local/companies/[company-slug].md`). Then run the rest of
`references/prep.md` as-is for round-specific depth — it already contains
everything this round needs. Do not re-derive company research or JD logic
here; `references/prep.md` and `references/research.md` are the single
source for both.

Write the full STAR+ story mapping, concerns-and-counters, and dossier notes
into the same company file's "HM / full-loop round" subsection under Prep
Answers by Round, replacing the "empty until then" placeholder.

## Where each round-specific part lives

All in `references/prep.md` unless noted:

- **Full STAR+ depth**: Step 8, via `references/story-mapping-engine.md`'s
  full portfolio optimization across the complete predicted-question set —
  not the Shared Core's 5-story shortlist.
- **Follow-up/probe handling**: the Interview Format Taxonomy and Format
  Discovery Protocol, plus probing patterns in `references/role-drills.md`.
- **Coverage checklist**: `local/hm-panel-checklist.md`, scored automatically
  via the COVERAGE lens in `references/rubric.md` on every graded mock answer.
- **Concerns-and-counters**: the Likely Concerns + Counters section of the
  Output Schema, sharpened further by the standalone `concerns [company]`
  command.
- **Dossiers**: the Interviewer Intelligence section, and the standalone
  `dossier [names]` command for full [FOUND]/[INFERred] research and each
  person's secret question. Mocks play the actual dossier personas per
  `CLAUDE.md`'s persona rule, falling back to `references/role-drills.md`
  archetypes only when no dossier exists.

## Live simulation

Runs through the existing `mock [format]` / `practice` commands
(`references/mock.md`, `role-drills.md`, `rubric.md`) using the personas and
predicted questions this file's prep produced. There is no separate `hm
mock` — the general mock engine already handles full STAR depth, follow-ups,
and persona-based simulation. `recruiter mock` exists as its own,
deliberately shallower engine because a screen behaves nothing like a
full-loop round.
