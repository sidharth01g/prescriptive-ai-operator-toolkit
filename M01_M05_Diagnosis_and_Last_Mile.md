# Module 1 · Diagnosis brief (prediction trap)  
# Module 5 · Last-mile placement patterns

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Briefs · v0.2 · Sep 2026

---

## Module 1 · Are you stuck in the prediction trap?

**Prediction** answers: what might happen?  
**Prescription** answers: what should we do next, under uncertainty, with an owner?

### Signs you shipped insight, not a decision
- [ ] Operators still open 3+ tools after the AI feature replies  
- [ ] Output is a score, paragraph, or chat with no next action  
- [ ] No abstain path when data is thin  
- [ ] Success measured by chat volume or fluency  
- [ ] Overrides are treated as user error instead of product signal  
- [ ] "We shipped AI" is the OKR, not a changed decision

### One-page diagnosis (fill in)

| Field | Answer |
|-------|--------|
| Workflow / decision | |
| Who owns the decision today | |
| Current AI output shape (score / chat / report) | |
| Where the operator actually decides | |
| Why the last mile fails (1 sentence) | |

### Minimum fix
Define one **decision object** (Module 2) for one workflow. Put it where work already happens (Module 5). Measure time-to-decision (Module 6). Gate knowledge quality (Module 4) before you trust the object.

### Anti-pattern list (refuse)
- Dashboard health color with no owner  
- Daily "insights" email with no pull moment  
- Model upgrade as the roadmap when last mile is unfinished  
- Chatbot bolted beside a system of record that holds the truth

---

## Module 5 · Where prescription lives

Three placement patterns beat a generic chatbot sidebar:

| Pattern | Where | Why it works |
|---------|-------|--------------|
| **1 · System of record** | Next to the account, deal, ticket, or trade already open | Operator is already deciding |
| **2 · Reporting path** | At "what changed?" | Turns report into next step |
| **3 · Exception queue** | Ranked list with owners and due actions | Matches how high-stakes work is triaged |

Pick **one** pattern for Crawl (Module 7). Do not ship all three at once.

### Account health as prescription (not a traffic light)
Emit: recommended conversation · driving signals with provenance · freshness · override path.  
Signal stacks without provenance become politics.

### Last-mile anti-patterns
- AI that contradicts an integrated feed it cannot read  
- Reports without a recommended next step  
- Health scores without an owner  
- Automation that skips system-of-record write-back  
- Separate "AI app" that forces context switching away from the decision surface

### Placement smoke test
If the operator must copy-paste the recommendation into another tool to act, last mile failed.

---

**Related:** Module 2 · Module 4 · Module 6 · Module 7–8
