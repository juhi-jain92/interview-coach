# AI PM Answer Frames

Expected content scaffolds for technical, system design, and trust questions.
The coach grades coverage against these and coaches toward them, without
turning answers into recitals. Compiled from cohort notes and prep material.

## Interview posture

- Business meeting, not audition: here is your problem, here is how I solve it.
- Reframe every answer in the stakeholder's KPI language.
- Surprise them with insights they don't have = hired. Matching them = maybe.
- The two pillars tested: AI Product Sense (ecosystem, the product, leadership)
  and AI Technical Fluency (concepts, system design). Interviews now run
  roughly 60% technical, 40% product and execution.
- The four rounds and their muscles: HM (production experience: idea to
  roadmap, evals, trust, GTM), System Design (end-to-end architecture and
  where it breaks at scale), Case with Leadership (judgment under ambiguity),
  AI Product Design (confidence display, failure states, earning trust).
- 2026 emphasis: harness design with costs, observability of MCPs/tool calls/
  multi-agent systems, instruction adherence, eval depth, continuous learning
  and memory for agents.

## The 7-step AI PM story structure (for presenting her own projects)

1. Workflow problem: what was slow, manual, inconsistent, risky, or limiting.
2. User and business impact: who suffered, what consequence.
3. Why rules were insufficient: deterministic parts vs parts needing
   interpretation, classification, retrieval, reasoning.
4. System design: inputs, context, data sources, model role, deterministic
   services, tools, orchestration, validation, human review, outputs.
5. Reliability design: golden dataset, metrics, thresholds, failure modes,
   guardrails, observability, reviewer override, rollback/escalation.
6. Product decisions: automation vs control, accuracy vs throughput, latency
   vs quality, generalization vs rules, build vs buy, MVP vs production.
7. Outcome: measured where available; projections labeled as projections.

Standard: don't explain what the model did. Explain why the workflow was
designed that way and how success or failure would be detected.

## TRUST framework (trust-in-AI questions)

- T: Target the moment of trust. Find where users decide to trust or abandon.
- R: Reduce cognitive load, not just add transparency. Progressive disclosure.
- U: Uncertainty as a UX feature. Graceful failure, no false confidence.
- S: Signal quality continuously. Confidence signals over raw accuracy stats.
- T: Tight feedback loops. Implicit signals wired into evals and iteration.

For trust-sensitive domains (legal, finance): show how humans do it manually,
citations with depth, editable reasoning so users feel like orchestrators,
evals comparing model vs competitor vs human.

## RAG vs Fine-Tuning vs System Prompting

- System prompting: static guardrails, logic, layout. Lowest cost.
- RAG: any runtime injection of external data into context (vector DBs AND
  plain API calls). Fresh facts, lowest hallucination when hard-grounded.
- Fine-tuning: permanent behavior/tone/syntax change. Frozen knowledge,
  highest cost and hallucination risk for facts.

Decision rules: use RAG for knowledge, fine-tuning for style. Fine-tuning for
knowledge is a failure point because it freezes data in time. Fine-tune for
strict output structure, brand voice, or latency/cost via smaller models.

## Defense-in-depth (public LLM safety)

Input guard (lightweight classifier) -> vector sieve of known attack patterns
-> intent separation (data wrapped as passive text vs instruction blocks) ->
output filter (regex + LLM-as-judge before render) -> anomaly observability
and honeypots. Assume the core model CAN be bypassed; catch at another layer.

## Agentic safety (chatbot -> autonomous agent)

Shift from content moderation to runtime access control: ephemeral sandboxing
(contained blast radius), deterministic gatekeeper proxy between agent and
APIs (hard limits prompts cannot bypass), HITL triggers on protected state
changes, transaction rollbacks to pre-agent state on anomalies.

## The harness ("models don't run code; wrappers run code")

Raw model = static frozen weights, no tools. Production systems wrap it:
input safety classifiers, intent routers, tool callers, context assembly,
output filters. Tool flow: model emits structured tool call -> orchestrator
executes -> result re-injected as context -> final generation. The LLM is the
cognitive router; deterministic software executes. This maps directly to her
diagnostic agent architecture: LLM for intent extraction and synthesis only,
deterministic harness for queries, validation, and severity ranking.

## Hard filters for any "should we build this with AI" question

1. Data readiness: volume, quality, lineage, labeling, legal access. If
   missing, feasibility is zero regardless of headcount.
2. Error tolerance: what happens on hallucination or misclassification.
   Low-tolerance domains demand HITL architecture that degrades ROI.
