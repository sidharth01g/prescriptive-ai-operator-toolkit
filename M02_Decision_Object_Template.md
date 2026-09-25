# Module 2 · Decision object template

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Fillable worksheet · v0.2 Sep 17, 2026 · Draft v0.2 · for practitioners  
**Use:** One screen for operators. If it needs a second tool to verify, the last mile is unfinished.

---

## Decision object (fill one per recommendation)

| Field | Your entry |
|-------|------------|
| **Decision type** (e.g. account triage, exception, admin action) | |
| **Recommended action** (what to do next · constrained catalog preferred) | |
| **Owner / role** | |
| **Due / time box** | |
| **Evidence / signals** (named sources · systems of record) | |
| **Freshness** (as-of times · SLA status) | |
| **Uncertainty / missing data** | |
| **Constraints** (policy, money, permissions, market rules) | |
| **Human gate required?** Y/N · why | |
| **Operator response** Accept / Modify / Override | |
| **Override reason code** (if not accept) | |
| **Audit log ID / link** | |

---

## Worked example (anonymized · account triage)

| Field | Example |
|-------|---------|
| Decision type | Account health triage |
| Recommended action | Schedule risk review with account owner this week (catalog: `RISK_REVIEW_7D`) |
| Owner / role | Customer Success Manager · named owner |
| Due / time box | 7 days from emission |
| Evidence / signals | Open Sev-2 tickets (n=3, last 14d) · complaint tags · usage drop vs 30d baseline · CST note sentiment |
| Freshness | Tickets as-of today · usage as-of T-1 · CST note 4d old (flagged) |
| Uncertainty / missing | No renewal conversation logged in last 45d |
| Constraints | No customer-facing email without AE · do not auto-credit |
| Human gate | Y · money and relationship risk |
| Operator response | (blank until acted) |
| Override reason code | e.g. `FALSE_POSITIVE_USAGE` · `ALREADY_IN_RECOVERY` |
| Audit log | System-generated id on accept/override |

---

## Operator check (30 seconds)

- [ ] I can paste this into a customer or compliance conversation without rewriting  
- [ ] Citations point to systems of record I already trust  
- [ ] If I override, the next human gets this same object (no Slack archaeology)  
- [ ] Abstain is available when evidence is thin or stale  

---

## Anti-patterns (do not ship as a "decision")

- Score or color with no next action  
- Fluent paragraph with no owner  
- Alert without a prescribed step  
- Recommendation that cannot be overridden with a reason code  
- Free-form model text that invents actions outside the catalog  

---

## Product rule (one line)

**Emit a decision object, not a prediction.** Predictions inform; decision objects assign action, evidence, owner, and override.

---

**Related modules:** Module 3 Trust contract · Module 6 Scoreboard · Module 8 Sprint playbook
