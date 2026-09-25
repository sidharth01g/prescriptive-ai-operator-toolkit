# Module 3 · Trust contract + 30-day plan

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Checklist · v0.2 · Sep 2026

---

## Sample trust contract clauses (adapt, then post where PM + eng + operators see them)

1. We will not recommend an action without a cited evidence set and a named owner.  
2. We will abstain when freshness or tenancy checks fail.  
3. We will log overrides and review them weekly without blaming the operator.  
4. We will measure silent failure, not only crashes and latency.  
5. We will not expand the decision surface until the current surface has a stable override pattern.  
6. Push alerts are reserved for high-severity exceptions with a prescribed next step.

**Signed / owned by:** _______________ **Date:** _______________

---

## Pull vs push (quick rule)

| Mode | When | Required |
|------|------|----------|
| **Pull** | Default for advisory recommendations | Decision object ready when operator asks |
| **Push** | High cost of miss · clear owner | Prescribed action + evidence · not a newsletter |

---

## Explainability operators will use

Answer these in the UI (not SHAP plots alone):

- [ ] What action is recommended?  
- [ ] Which inputs and documents matter?  
- [ ] What is missing or stale?  
- [ ] What happens if the operator overrides?  

If the explanation cannot be pasted into a customer or compliance conversation, rewrite it.

---

## Worked example (account-health surface)

| Clause in practice | What "done" looks like |
|--------------------|------------------------|
| Evidence + owner | Every elevated risk emits Module 2 object with CSM owner |
| Abstain | No recommendation if usage feed is >48h stale or ticket permissions missing |
| Override review | Friday 20-min review of reason codes · top 3 become backlog items |
| Silent failure | Track "operator ignored recommendation" rate, not only API errors |
| Narrow surface | Only `RISK_REVIEW_7D` and `ESCALATE_SUPPORT` in catalog for month 1 |
| Push | Only Sev-1 / regulatory deadline misses push · everything else pull |

---

## First 30 days after launch

| Week | Focus | Done? |
|------|-------|-------|
| 1 | Ship one narrow decision set · watch whether operators pull it before expanding | [ ] |
| 2 | Review every override with the operator · treat reasons as requirements | [ ] |
| 3 | Publish one note: abstains, wrong answers, what changed | [ ] |
| 4 | Kill one noisy alert or ungrounded surface · keep only what earns attention | [ ] |

If you cannot staff the weekly review, do not broaden rollout.

---

## Anti-patterns

- Trust docs that never appear in the decision moment  

- Push storms: dozens of "AI insights" with no prescribed action  
- Blame the user for overrides instead of treating them as product signal  

---

**Related:** Module 2 Decision object · Module 6 Scoreboard
