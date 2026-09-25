# Module 7 · Maturity ladder diagnostic  
# Module 8 · One-week Crawl plan + kill criteria

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Diagnostic + plan · v0.2 Sep 17, 2026 · Draft v0.2 · for practitioners

---

## Maturity ladder (pick one label per workflow · no vanity)

| Rung | Must be true | Our workflow: _______________ |
|------|--------------|-------------------------------|
| **Crawl** | One narrow workflow · SoR grounding · human gate · abstain/override measured · decision object written | [ ] |
| **Walk** | Related workflows share evidence foundation · provenance in UI · pre/post eval · dual track sandbox vs prod | [ ] |
| **Run** | Prescription in daily workflow · audit trails · continuous silent-failure eval · time-to-decision improved on baseline | [ ] |

**Exit criteria**

| Move | Exit when |
|------|-----------|
| Crawl → Walk | Second workflow reuses same grounding + owner model |
| Walk → Run | Decision objects live in SoR / reporting / exception queues · weekly override review is routine |

**Sandbox vs production:** experimental agents cannot change money, commitments, or access without production bars.

---

## One-week Crawl plan

| Day | Task | Owner | Done | Evidence link |
|-----|------|-------|------|---------------|
| 1–2 | Pick one workflow + one owner | | [ ] | |
| 3–4 | Wire grounding + decision brief (Module 2) | | [ ] | |
| 5 | Human gate + override reason codes | | [ ] | |
| 6–7 | Measure abstain/override · ship only if operators pull | | [ ] | Module 6 scoreboard |

Then stop. Do not add a second workflow until Crawl holds.

---

## Stakeholder script (meeting answers)

1. Which operator decision are we changing this quarter?  
2. What is baseline time-to-decision today?  
3. What evidence sources and freshness SLA do we need?  
4. Where is the human gate, and who owns overrides?  
5. Which vanity metrics will we refuse to report as success?  

If the room cannot answer (1) and (4), pause the build.

---

## Kill criteria (write into the ticket before ship)

| Trigger | Action |
|---------|--------|
| Override rate above ____% with the same missing-field reason for 2 weeks | Fix data or kill surface |
| Silent-failure catches rising after a content change | Roll back index/prompt before adding features |
| Operators stop pulling the decision object | Interview + narrow · do not expand scope |
| Time-to-decision flat after 30 days in Crawl | Kill or redesign; do not Walk |

Fill blanks from Module 6 before launch review.

---

**Related:** Module 2 · Module 4 · Module 6
