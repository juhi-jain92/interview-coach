# Interview Coach for AI PM Roles

A Claude Code interview coaching system for senior AI Product Manager
interviews. Open this folder in Claude Code and you are talking to a coach
that runs mocks, drills, story interrogations, transcript analysis, and
progress tracking, with persistent memory across sessions.

Built on [Noam Segal's interview-coach](https://github.com/noamseg/interview-coach-skill)
(MIT) as the backbone, then extended and personalized. This repo is the
framework; all personal data (profile, stories, scores, limitations) lives in
a gitignored local layer, so the system is publicly shareable while the
candidate is not in it.

## Quickstart

1. Clone, open the folder in Claude Code.
2. Create your local layer: `local/profile.md` (positioning, verified numbers,
   accuracy flags), `local/story-bank.md` (STAR stories),
   `local/juhi-context.md` equivalent (story slots, scripts). See
   `references/coaching-state-schema.md` and `references/storybank-guide.md`.
3. Say `mock panel`, `drill`, `grill [story]`, or just describe what you need.
   State persists to `coaching-state.md` automatically.

## Commands

decode, research, dossier, prep, mock, practice/drill, grill, concerns, hype,
debrief, analyze, progress, stories, feedback, thankyou. Plain English works;
the router detects intent. Full registry in `CLAUDE.md`.

## Enhancements over the original

1. **Grill**: a design-tree interrogation command (adapted from a personal
   grill-me skill). Maps one story as a tree of decisions and walks the
   frontier in rounds until no branch is unresolved. Prep mode resolves gaps
   with recommended answers; prosecute mode drills them in the interviewer's
   voice. Built for the project deep-dive, the highest-signal part of PM
   interviews.
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
   survivability across three follow-ups). Carried over from the author's own
   interview-prep skill; it explains WHY a dimension scored low.
5. **Real-person interviewer dossiers**: mocks and drills play the actual
   people in the loop, researched with evidence-labeled claims and each
   person's "secret question," falling back to generic archetypes only when
   no dossier exists. Also from the author's prep skill.
6. **Spoken-answer-first judging**: answers are dictated and judged as speech,
   never as writing. Three load-bearing sentences, then stop.
7. **Compiled AI PM question bank and answer frames**: a tagged bank of
   interview questions and case scenarios gathered from multiple sources
   (see Credits), organized by the dimension each one tests and paired with
   expected answer scaffolds (story structure, trust framework, RAG vs
   fine-tuning decision rules, safety architectures, pricing tenets) the coach
   grades coverage against. The contribution here is the tagging, dimension
   mapping, and integration into the two-lens rubric, not the source
   questions themselves.
8. **Locked-profile pattern**: all factual claims trace to a single local
   profile file with explicit accuracy flags (what the candidate can and
   cannot claim), so prep material can never train overclaiming.
9. **Public/private split**: the gitignored local layer keeps all personal
   data (profile, stories, scores, weakness log) off GitHub, making the
   framework shareable as a portfolio piece without exposing the job seeker.

## Credits

- **Noam Segal**: the interview-coach backbone this is built on: session
  state system, calibration engine, drill progression ladder, command
  architecture, rubric anchors. MIT licensed; original license preserved in
  `LICENSE`.
- **Mahesh Yadav (Agentic AI Institute)**: the hiring-manager evaluation
  checklist this repo's coverage lens adapts, the bulk of the AI PM interview
  questions and case scenarios in the question bank, and the interview
  bootcamp structure that shaped the prep philosophy. Questions are compiled
  and credited here as study material; the framework around them is this
  repo's contribution.
- Additional question-bank items are gathered from public PM interview
  resources and the author's own practice notes.
- Additional consolidation and the enhancements above.

## License

MIT. See `LICENSE`.
