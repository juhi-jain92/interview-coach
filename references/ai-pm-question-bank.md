# AI PM Question Bank

Compiled from Mahesh Yadav's cohort daily FAQs (Days 1-21) and case material
(credited in README). Tags map to local/hm-panel-checklist.md dimensions:
[ECO] Ecosystem, [CON] Concepts, [BLD] Building, [SYS] System Design,
[BEH] Behavioral, [CASE] Case scenario.
GAP-RISK = answer honestly via Gap-Handling Module (cross-cutting.md);
never overclaim past profile.md accuracy flags.

Selection rules: weight toward active interview-limitations, storybank gaps,
the target company's logged patterns, and low-coverage dimensions. Substitute
the bracketed company with the actual target when known.

## Ecosystem and strategy [ECO]

1. How do you evaluate whether AI is needed or the solution is better without AI?
2. There's no moat in AI agents since everyone builds on the same models. How do you build defensibility?
3. Is building your own model a good way to create a moat? Competitors use "own model" for trust but we see no accuracy gains. Build or keep leveraging OpenAI/Anthropic?
4. Where will AI have the highest impact in the next 2 years: Q&A products, workflow automation, or full workforce automation? Rank and defend.
5. Infra layers: foundation models, tools/orchestration, agents-as-a-service. Where should [company you're interviewing with] play and why?
6. How do you see AI changing the B2B software landscape and where can we play?
7. You're presenting 2026 strategy to the Google Cloud CEO. Core investments to make, and what to stop?
8. What's your take on MCP servers: all-in or skeptical? Why?
9. Rank verticals for building AI agents first: healthcare, entertainment, legal, e-commerce. Justify.
10. How do you see agent-to-agent communication evolving?
11. How do you overcome the cold start problem in AI agents?

## Concepts and technical fluency [CON]

12. Explain in simple, non-jargon terms how ChatGPT/Gemini was built.
13. Is hallucination in AI agents a feature or a bug?
14. How does training work for LLMs? When does fine-tuning meaningfully beat prompt engineering or retrieval?
15. What are SLMs? Advantages and disadvantages?
16. What are the main failure points in agentic systems?
17. What are the various costs of building AI agents beyond inference? (List 6-7 modules.)
18. How do you calculate the base cost of running an AI agent in production? True unit economics?
19. What context does a system need to answer "How many holidays do I have pending?"
20. RAG vs fine-tuning vs system prompting: how do you choose? (Frame in answer-frames.md.)

## Building: experience-anchored [BLD]

21. How have you managed context in AI agents you built?
22. What challenges have you seen managing RAG-based agents, and how did you help engineering resolve them?
23. How do you build user trust when building an AI agent? (TRUST frame.)
24. Walk us through how you set up evaluation for AI agents, and three key learnings from running evals in real systems.
25. Explain your context management pipeline plus 3 core challenges (context injection, tool calling, multi-turn memory).
26. Three core learnings from working with ML engineers/researchers on improving AI agent quality.
27. How have you helped manage costs in multi-call agent workflows (classify, extract, judge, risk-check)?
28. Pick a project from your CV: how did you track progress and align researchers and ML engineers to create value while saving cost?
29. How do you detect tool misuse by agents? What observability and eval requirements ensure success?
30. How will you ensure our customer-support agent (financial institution) doesn't go rogue in public?
31. How have you scaled evaluations beyond humans, especially red teaming? GAP-RISK
32. How did you scale evaluation from beta (1-5% of users) to 100% launch at 10,000+ conversations/day? GAP-RISK
33. Walk me through your HHH (helpful, honest, harmless) evaluation details and learnings. GAP-RISK
34. Draw and explain a system diagram for a multi-agent system you worked on. [SYS] GAP-RISK
35. What are three things you considered when pricing your AI agents?
36. What's your data strategy for AI agents you built (e.g., a contract risk analyzer)?
37. How do you drive adoption for AI agents in an enterprise SaaS beyond initial hype?
38. How would you design a team structure to succeed in the AI agentic world?

## System design [SYS]

39. Create a system design for AI agents with knowledge bases, tools, and memory.
40. Walk us through the system design of a contract risk assessment agent (upload contract, get risks and key terms). Map to her AI Troubleshooting Agent architecture: LLM for intent/synthesis only, deterministic orchestration harness for execution, validation, ranking.
41. Reverse-engineer a system diagram of a question-answering app like Glean.
42. Design a metrics dashboard: north star plus L1, L2, L3 metrics for an AI agent.

## Behavioral [BEH]

43. Tell me about a time you helped engineering fail fast and ship faster.
44. What would you do if a competitor copied our product at lower cost?
(Full behavioral coverage comes from local/story-bank.md mapping; these two
came tagged from the cohort. Growth-mindset rubric applies.)

## Case scenarios [CASE]

45. Copilot retention case: PM of MS Word Copilot, move retention 15% to 40% in 6 months. Strong answer: clarify and decompose (why 40? competitive need?), options with eval plan, golden dataset with key scenarios, data flywheel (hypothesis -> measure -> product improvement), tradeoffs and guardrails, tie back to north star.
46. LegalBot case: flat-fee enterprise AI tool, margins fell 75% to 40% from power-user compute, plus confident hallucinations. Diagnose (isolate gross margin, segment cohort, find pricing flaw), restructure to three-tier outcome-priced model with soft-landing migration, re-architect for trust (hard-grounded RAG, LLM-as-judge, lineage/observability, HITL sign-off). Key lines: follow the margin; never price the input, price the outcome; never hide the probability, design the safety net.
47. Legacy company, 5 executive AI ideas, limited resources. Strategic fit vs feasibility matrix; filters: data readiness, error tolerance, business impact, build vs buy. High-value high-feasibility first, HITL to bypass early accuracy limits.
48. Public-facing LLM app: protect against prompt injection, jailbreaks, brand damage. Defense-in-depth pipeline (answer-frames.md).
49. Chatbot to autonomous agent (reads email, executes APIs): how does safety architecture change? Runtime access control pillars (answer-frames.md).
50. How does Perplexity build defensibility on the same base models?
51. Pricing model for AI agents automating Tier-1 support for Amazon returns: compare approaches on cost predictability, customer value, operational complexity, scalability.
52. Inference costs $0.10/request on a frontier model. Expected cost if you fine-tune a custom version and host on Azure? Evaluate via cost, control, latency, scale.
53. US defense contractor extracting insights from documents in remote operations: proprietary cloud models vs open-source on edge vs custom fine-tuned open-source. Choose a sequencing path and justify.
54. Critique lovable.dev pricing and suggest better, using tenets: value > usage, long-term > short-term profitability, land-and-expand > one-time.
55. Reverse-engineer manus.ai adoption to $100M ARR: differentiated experience, where they played despite Claude/OpenAI/Perplexity, how usage compounds quality.
56. Move a contract-risk-tracker agent from per-contract usage pricing to value-based pricing. How?
57. Compare eval/observability platforms (Azure AI Foundry, AWS AgentCore, LangSmith): define your comparison tenets first.
58. Precision vs recall calls: for a given problem, recommend one and justify with three bullets.

## Expected answer frames for the pricing cluster (35, 51, 54, 56)

Value metric first (the moment the customer says "worth it"), then: value >
usage, long-term > short-term profitability, land-and-expand with repeated
use cases, unit economics floor (inference + beyond-inference costs), never
price the input.
