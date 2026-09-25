# Module 6 · Operator scoreboard worksheet

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Worksheet · v0.2 · Sep 2026

---

## Demo metrics vs operator metrics

| Demo (hygiene only) | Operator (product success) | Your baseline | After ship |
|---------------------|----------------------------|---------------|------------|
| Answer latency on happy path | Time-to-decision under partial data | | |
| Fluency / "wow" | Exception rate + recovery time | | |
| # of AI features | Override rate with reason codes | | |
| Pilot NPS | Auditability when something goes wrong | | |
| Tokens / chats | Repeat use in real decision moments | | |

**Rule:** if a metric can improve while operators still make the same decision late or wrong, it is demo hygiene, not success.

---

## Minimum viable scoreboard (track these five)

| # | Metric | How you measure | Owner | This week | Target / kill line |
|---|--------|-----------------|-------|-----------|--------------------|
| 1 | Time-to-decision vs baseline (top 3 decision types) | Clock from trigger → committed action in the system of record | | | |
| 2 | Override rate + reason codes | Count overrides · top 3 codes weekly | | | |
| 3 | Abstain rate (thin retrieval / stale data) | Abstains ÷ eligible decision moments | | | |
| 4 | Silent-failure catch rate in eval (pre + post release) | Wrong-but-plausible caught ÷ injected cases | | | |
| 5 | Repeat use in decision moments (not chat opens) | Sessions that end in a logged decision object | | | |

Fill **Target / kill line** before the first weekly review. Empty cells after two reviews = pause feature work.

---

## Weekly operating review (30–45 min)

1. Top overrides and why  
2. Abstains that frustrated operators  
3. Silent-failure catches from the eval harness  
4. One decision-object improvement to ship next  

**Date of review:** _______________ **Attendees:** _______________

**Decision this week:** Keep · Narrow · Kill surface _______________

---

## Vanity KPIs to refuse

- [ ] Tokens generated / chat sessions as success  
- [ ] Hours "saved" without a baseline workflow  
- [ ] Self-report surveys as the only productivity measure  
- [ ] "AI features shipped" as the OKR  
- [ ] Model leaderboard score without operator outcome  

---

## Tie-back

- Module 2 defines the decision object you are scoring.  
- Module 4 gates knowledge quality before you trust metric (4).  
- Module 7–8 sets Crawl exit and kill criteria using this sheet.
