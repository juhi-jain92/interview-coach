# Interview Coach for AI PM Roles

A Claude Code interview coaching system for senior AI Product Manager
interviews. Open the folder in Claude Code and you are talking to a coach that
researches the company, preps you for a specific job description, runs
practice interviews, interrogates your stories until they hold, scores your
answers, tracks your weak spots, and remembers all of it across sessions.

Built on [Noam Segal's interview-coach](https://github.com/noamseg/interview-coach-skill)
(MIT) as the backbone, then consolidated with material from an AI PM interview
cohort and the author's own coaching skills. This repo is the framework; all
personal data (profile, stories, scores, weaknesses) lives in a gitignored
local layer, so the system is publicly shareable while the candidate is not
in it.

## What it does, plainly

- **Preps you for a specific interview.** Give it a job description and it
  researches the company, pulls out the keywords that matter, picks the
  handful of your stories that fit the role, and maps your experience to their
  problems in their language.
- **Runs practice interviews, out loud.** Recruiter screens, hiring-manager
  rounds, panels, system design. It plays the interviewer, asks one question
  at a time, and grades you at the end, like the real thing.
- **Scores every answer two ways:** whether you said it well (delivery) and
  whether you said what they needed to hear (coverage), so you know if a weak
  answer was a performance problem or a knowledge gap.
- **Interrogates your stories until they hold.** The grill command maps one
  story as a tree of decisions and picks at every number and choice until
  nothing can be poked, so an interviewer can't find a hole you didn't.
- **Learns your weak spots and drills them.** It tracks the patterns that cost
  you (burying your impact, rambling past the point) and aims future questions
  at them, retiring each once you've fixed it.
- **Keeps a running doc per company** so prep builds across rounds instead of
  restarting each time.
- **Never lets you overclaim,** because every factual claim traces to one
  locked profile of what is true about your experience.

## How it is built

One always-loaded brain file (`CLAUDE.md`) reads your command and opens the
right instruction sheet from the `references/` folder. Those detailed sheets
are pulled only when needed, so the always-on footprint stays small. Your
private data (profile, stories, scores, weaknesses) lives in a gitignored
`local/` layer that never reaches GitHub. The framework is shareable; you are
not in it.

## Quickstart

1. Clone, open the folder in Claude Code.
2. Create your local layer: `local/profile.md` (positioning, verified numbers,
   accuracy flags), `local/story-bank.md` (STAR stories), and your context
   file (story slots, scripts). See `references/coaching-state-schema.md` and
   `references/storybank-guide.md`.
3. Say `recruiter prep [company]`, `mock`, `grill [story]`, or just describe
   what you need. State persists to `coaching-state.md` automatically.

## Commands

Prep and research: `decode` (a JD), `research` (a company), `dossier`
(interviewers), `prep`, `recruiter prep` / `recruiter mock` (recruiter
screens), `hm` (hiring-manager and full-loop rounds).

Practice: `mock` (full simulated interview), `practice` / `drill` (gated drill
ladder), `grill` (story interrogation), `concerns` (interviewer concerns and
counters).

Around the interview: `hype` (pre-interview confidence from real score data),
`debrief` (same-day capture), `analyze` (deep transcript scoring), `progress`
(trend review and calibration), `stories` (storybank management), `feedback`,
`thankyou`.

Plain English works; the router detects intent. Full registry in `CLAUDE.md`.

## Enhancements over the original

1. **Grill**: a design-tree interrogation command adapted from
   <https://www.aihero.dev/use-the-grill-me-skill-k029d>. Maps one story as a
   tree of decisions and walks the frontier in rounds until no branch is
   unresolved. Prep mode resolves gaps with recommended answers; prosecute
   mode drills them in the interviewer's voice. Built for the project
   deep-dive, the highest-signal part of PM interviews.
2. **Self-updating limitations loop**: `interview-limitations.md` tracks
   active weakness and strength patterns with evidence. Two-occurrence rule to
   earn a line, three-clean-sessions rule to retire one. Every mock, drill,
   and grill reads it first and weights questions toward active watches; the
   pre-interview hype command reads only the strengths section.
3. **Two-lens scoring**: every answer is scored on two independent axes,
   delivery (the five dimensions from the base rubric) AND coverage (whether
   the answer said what the hiring manager was listening for, scored against
   an interviewer checklist). The base system scores delivery only; splitting
   coverage out lets score history distinguish a performance problem from a
   content gap, which need different fixes.
4. **Seven-check tactical layer**: under the delivery dimensions sits a
   seven-point diagnostic applied to every spoken answer (length and the
   three-sentence rule, intended bullets landed, keyword match, impact
   position, junior-signal tells, number attribution under pressure,
   survivability across three follow-ups).
5. **Spoken-answer-first judging**: answers are dictated and judged as speech,
   never as writing. Three load-bearing sentences, then stop.
6. **Dedicated recruiter and hiring-manager tracks over a shared prep core**:
   company research, JD parsing, keyword mapping, and story selection live
   once as a shared core; recruiter and HM are thin wrappers that add only
   their round-specific depth and sections. Recruiter mode adds a
   forwarded-notes test (would this answer survive a non-technical recruiter
   paraphrasing it to the hiring manager) and handles relayed follow-ups.
7. **Per-company running docs**: each target company gets a persistent doc
   holding research, JD keyword map, mapped stories, and per-round prep
   answers, built from a public template with filled instances kept private,
   so prep compounds across rounds.
8. **Compiled AI PM question bank and answer frames**: a tagged bank of
   interview questions and case scenarios gathered from multiple sources
   (see Credits), organized by the dimension each one tests and paired with
   expected answer scaffolds (story structure, trust framework, RAG vs
   fine-tuning decision rules, safety architectures, pricing tenets) the coach
   grades coverage against. The contribution here is the tagging, dimension
   mapping, and integration into the two-lens rubric, not the source
   questions themselves.
9. **Locked-profile pattern**: all factual claims trace to a single local
   profile file with explicit accuracy flags (what the candidate can and
   cannot claim), so prep material can never train overclaiming.
10. **Public/private split**: the gitignored local layer keeps all personal
    data (profile, stories, scores, weakness log) off GitHub, making the
    framework shareable as a portfolio piece without exposing the job seeker.

## Credits

- **Noam Segal**: the interview-coach backbone this is built on: session
  state system, calibration engine, drill progression ladder, command
  architecture, rubric anchors. MIT licensed; original license preserved in
  `LICENSE`.
- **Mahesh Yadav (Agentic AI Institute)**: <https://maven.com/mahesh-yadav>
  the hiring-manager evaluation checklist this repo's coverage lens adapts,
  the bulk of the AI PM interview questions and case scenarios in the question
  bank, and the interview bootcamp structure that shaped the prep philosophy.
  Questions are compiled and credited here as study material; the framework
  around them is this repo's contribution.
- **Matt Pocock**: <https://www.aihero.dev/>
- Additional question-bank items are gathered from public PM interview
  resources and the author's own practice notes.
- Additional consolidation, architecture, and the enhancements above by the
  author.

## License

MIT. See `LICENSE`.
