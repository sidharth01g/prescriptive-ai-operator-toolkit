# Module 9 · Shared learnings, turned into a prescription

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Synthesis · v0.3 · Sep 2026

This module is an original reading of public ship notes. It is not a case study of any one company, and it does not reuse their metrics. The contribution is the map: take a lesson someone else published, and force it into a constrained action this toolkit already knows how to ship.

---

## What I read (Sep 27, 2026)

People are publishing the same kind of note: the demo worked, production did not, here is what they would do first next time.

| Source | What they shared | Link |
|--------|------------------|------|
| Towards AI, production agent notes | Failure showed up in messy data and missing fallbacks, not in the model brand | https://pub.towardsai.net/why-ai-agents-fail-in-production-lessons-from-shipping-7-agents-across-healthcare-logistics-and-ac60dbd8b31d |
| Vectara, agent-failure case notes | A loop needs a hard stop. A spend dashboard is not a stop | https://github.com/vectara/awesome-agent-failures/blob/main/docs/case-studies/langchain-a2a-47k-infinite-loop.md |
| Practitioner agent postmortem | Approval should be tiered. Not every action needs a human, and not every action should be automatic | https://cloudynamics.hashnode.dev/agents-gone-wrong-what-i-learned-shipping-ai-agents-to-production-and-breaking-things-along-the-way |
| Signal, demo-to-deployment note | Run beside the human first. Treat tool access like a permission boundary. Define what happens when the agent fails | https://www.readsignal.io/article/agentic-ai-demo-to-deployment-what-broke |
| Dinesh Challa, AI PM notes | Escalation thresholds and acceptable error are product decisions | https://www.dineshchalla.dev/advice-new-ai-product-managers/ |
| Siddharth Mishra, eval notes | The eval cases outlast the prompt. If you cannot tell a regression, you are not ready to ship | https://mishrasiddharth.com/2026/03/19/the-eval-pipeline-is-the-product/ |
| Stanford Digital Economy Initiative, enterprise AI playbook | Teams that moved used short iterations and treated the pilot as an experiment | https://digitaleconomy.stanford.edu/app/uploads/2026/03/EnterpriseAIPlaybook_PereiraGraylinBrynjolfsson.pdf |

Read them for the pattern. Do not paste their numbers into your roadmap or your petition.

---

## Where the public notes agree

Six points show up often enough to treat as design rules. Each one already has a home in this toolkit.

1. **The model is not the product.** The useful work is the boundary around it: what it may do, how you know it failed, and who commits the action. Use Module 2 (decision object) and Module 4 (knowledge gates).
2. **Keep the action list small.** If a rule can decide it, do not hand it to a model. New action types are a process change, not a chat reply. Use the catalog in the architecture notes and Module 7 (Crawl: one workflow).
3. **A human gate is a tier, not a slogan.** Read-only can pass. Money, access, and irreversible writes need a named person. Use Module 3 (trust contract).
4. **Silent failure is the incident.** A fluent wrong answer, a loop, or a stale citation has to abstain or escalate in the product, not in a postmortem slide. Use Module 4 and Module 6 (abstain and silent-failure on the scoreboard).
5. **Watching spend is not the same as stopping spend.** Caps and iteration limits have to refuse the next call. A chart after the invoice is too late. Put the stop in the runtime, and record it on the decision object.
6. **Ship beside the operator before you ship instead of them.** A short shadow period builds the eval cases and the override log you will retrain on. Use Module 8 (one-week Crawl) before any second workflow.

---

## Original piece: one public lesson becomes one prescription

Do this when you read someone else's postmortem. Do not adopt their stack. Extract one constraint you can enforce.

| Step | Fill in |
|------|---------|
| Source (title + URL) | |
| Their lesson in one sentence (your words) | |
| Which of the six rules above it matches | |
| Catalog action you would emit (`SPIKE`, `CUT_SCOPE`, `ABSTAIN`, …) | |
| What the human must accept before it runs | |
| What you will measure in the next weekly review (Module 6) | |
| What you will not copy from them (their metric, their customer, their architecture) | |

If you cannot name a catalog action, the lesson is still a story. It is not yet a contribution you can operate.

---

## Worked example (synthetic, from the pattern, not from one article)

| Step | Entry |
|------|--------|
| Lesson | Two agents can call each other until the bill arrives |
| Rule | 5. A dashboard is not a stop |
| Catalog action | `ABSTAIN` until a hard iteration cap and a named owner exist. Then `SPIKE` to add the cap |
| Human gate | EM accepts the cap before any production tool with write access |
| Measure | Count of runs that hit the cap, and whether the operator got a visible stop instead of a silent retry |

---

## How to use this with the rest of the pack

1. Pick one public note from the table.
2. Fill the worksheet once.
3. If the action is real, put it on the Module 8 Crawl plan for a single workflow.
4. Do not add a second workflow until that cap, gate, or eval case has survived a week.

**Related:** Module 2 · Module 3 · Module 4 · Module 6 · Module 8
