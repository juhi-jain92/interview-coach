# recruiter [company]: Recruiter Screen Prep and Mock

A recruiter screen is a different animal from an HM round: 15-30 minutes,
fast, broad not deep, half of it the recruiter selling the role to you. They
usually don't have deep technical judgment, but they RECORD everything and
forward notes to the hiring manager, often close to verbatim. So the bar is
not brilliance; it is coverage, clarity, and answers that survive being
paraphrased by a non-technical person without losing the point.

This command has two modes: `recruiter prep [company]` and
`recruiter mock [company]`. Prep first, then mock.

## The governing rule: forwarded-notes test

Every answer is scored partly on: would this survive a non-technical person
retyping it into an email to the HM? That means:
- The number and the impact must be in the first sentence, before any setup.
- No unexplained jargon a recruiter can't spell or paraphrase.
- One crisp claim per answer, not three woven together.
If an answer only works when SHE delivers it with full context, it fails the
test. Rebuild it shorter and blunter.

## recruiter prep [company]

Read: local/profile.md (accuracy flags are law), local/story-bank.md,
local/career-narrative.md, coaching-state.md, the JD, and recruiter notes if
provided. Run the Shared Core from `references/prep.md` (steps 1-5: company
research prioritizing the blog step for speed, JD drill-down, JD keyword
coverage sweep, the 5-story selection, and where-you-fit mapping in their KPI
language). Do not re-derive that logic here. Then produce exactly these
round-specific sections.

### 1. TMAY (Tell Me About Yourself)
Use the TMAY frame in answer-frames.md. Structure:
- Past-and-future logline, 1-2 sentences: "I'm X, and I've worked on Y,"
  where Y explicitly names the JD's core problem she has already solved.
- Curiosity check: a short line inviting the recruiter to steer, so the 15
  minutes cover what THEY most need ("what would be most useful to cover in
  our time?").
- Stakeholder hook: fold the type of stakeholder this role serves into the
  intro to pique interest.
Rule: use real stories showing she is the key to THEIR problem, with where
she's already applied it. If there's no relevant experience, pivot to how she
would approach it, never fabricate. Grade the drafted TMAY against the frame.

### 2. Likely recruiter questions (5-8) with answers
Generate from the JD, company domain, and the question bank. Draw the "walk
me through a relevant project" answers from the Shared Core's 5-story pool
(step 4), not the full storybank — a screen doesn't need portfolio breadth.
For each: question, her answer at LOGLINE depth (30-60 seconds, not full
STAR), metric, tradeoff if relevant, stakeholders named. Cover: a core "walk
me through a relevant project," a domain-fit question about their business,
and at least one lightly technical probe (see section 4).

### 3. JD keyword coverage
Already swept in the Shared Core (`references/prep.md` step 3) against build
vs buy, RAG, prompt engineering, evals, identity/privacy, 0-to-1, and named
platforms, with each term mapped to a backing story or flagged as a gap.
Surface the results here at logline depth: one short answer per term, and
the honest bridge (Gap-Handling Module, cross-cutting.md) for any flagged
gap. Do not re-sweep the JD here.

### 4. Light-technical tier
Recruiter-level technical, not system design. Shallow but real: "have you
worked with LLMs / RAG / agents," "what's your experience with X platform."
Answers stay conversational and jargon-controlled (forwarded-notes test).
Pull from the ecosystem and concepts tags in the question bank, at the
simplest depth.

### 5. Why you're looking / what you're looking for
From career-narrative.md. Lead with the decision, not the departure. Forward-
looking, not apologetic. Keep it to 2-3 sentences.

### 6. People leadership (leadership-track roles only)
If the JD implies scope over people or the profile targets Principal/Staff,
prep a short team-leadership logline (the APM growth story) tied to the JD's
leadership expectation.

### 7. Your questions for them (must-ask)
Why the role is open, ownership vs delivery, employment type, direct reports,
timeline. These double as fit-screening for her.

### Compensation note
If comp comes up (it often does in screens), this command does NOT script a
number. Defer to the job-strategy skill's profile.md comp decisions. The
coach's only job here: flag if she under-anchors or softens on the number
when it appears, since that is a known growth edge. Naming it, not scripting
it.

## recruiter mock [company]

Simulate the screen live. Rules:
- Fast pace, back-to-back questions, minimal warmup, the way real recruiters
  stack them. No feedback mid-mock.
- Open with TMAY, always. It's the highest-leverage 30 seconds of a screen.
- One question at a time. Play the recruiter register: warm, broad, not
  technically deep, but probing on fit and clarity.
- Occasionally (not every session) inject 1-2 relayed follow-ups: a question
  passed along verbatim from the hiring manager, going somewhat deeper than a
  normal screen question but never to full technical depth. Pull these from
  `local/hm-panel-checklist.md` or `references/ai-pm-question-bank.md`.
  Deliver it flatly, as if reading from notes the recruiter doesn't fully
  understand: no ability to engage with the answer, no follow-up-to-the-
  follow-up, no technical push-back. Cap at two per mock. This tests handling
  a relayed probe secondhand, not surviving a technical round.
- Judge answers as SPOKEN (dictation). Three load-bearing sentences, then stop.
- Score each answer on both rubric lenses PLUS the forwarded-notes test.
- Weight questions toward active watches in interview-limitations.md,
  especially buried-lead and answer-scope-expansion, which the fast pace and
  the forwarded-notes rule punish hardest.
- On stop: standard session readout (rubric.md), plus one line on whether her
  notes would land well with the HM, plus append any 2x-observed pattern to
  interview-limitations.md.

## After a real screen
Run `debrief` same day: log questions asked, comp discussion if any, signals,
outcome. Feeds the outcome log and calibration engine.
