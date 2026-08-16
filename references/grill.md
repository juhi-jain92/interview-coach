# grill [story or project]

Design-tree interrogation of ONE story until no branch is left unresolved.
Adapted from the grill-me skill. This is what a bar raiser or skeptical HM
does to a project story; do it first, before they can.

## The tree

Map the story as a design tree: every decision branches into the decisions
that hang off it. For a product story the trunk splits into: problem framing,
alternatives considered, the chosen design, resourcing and influence, metrics
and their derivation, risks and failures, and what happened after. Every
number is a branch. Every "we decided" is a branch (who is we, why then, what
was rejected).

Work in ROUNDS. The FRONTIER is every question whose prerequisites are
settled. Ask the whole frontier in one numbered round, then wait. Answers
reshape the tree and push the frontier outward. A question depending on an
open question belongs to a later round. Done when the frontier is empty:
nothing silently assumed.

Fact-finding is the coach's job first: before asking anything, pull what is
already settled from local/story-bank.md, local/profile.md, and
coaching-state.md. Never ask what those files answer. Decisions and memories
are the candidate's; put those to the candidate and wait.

## Two modes

### grill prep (default)
Purpose: resolve her own story gaps before the room finds them.
Format per question:

Q1 - <title>: <question, may include choices>
Recommended answer: <the coach's best-guess resolution she can accept or
correct>

End state: an updated story with every branch defended, plus a list of any
branches that CANNOT be defended (per profile.md accuracy flags) with the
concede-transfer-close rebuttal line for each. Offer to save deltas to
local/story-bank.md.

### grill prosecute
Purpose: hard drill. Same tree mechanics, no recommended answers, questions
delivered in the target interviewer's voice (use dossier register when it
exists). Push each number until it holds or breaks. Score answers with
references/rubric.md (both lenses). On stop: session readout, and any pattern
observed twice goes to interview-limitations.md.

## Rules

- Read interview-limitations.md first; open branches inside active weaknesses
  get priority in the frontier.
- Questions tagged GAP-RISK anywhere in the story route through the
  Gap-Handling Module (cross-cutting.md): concede the true thing, show what
  transfers, close the rest. Never coach an overclaim.
- Spoken-answer rules apply in prosecute mode: judge as spoken, three
  load-bearing sentences, then stop.
- This complements, not duplicates, the challenge protocol: challenge red
  teams a story top-down with five lenses; grill walks the tree bottom-up
  until empty. Run challenge after grill when the story is high-stakes.
