# Module 4 · Knowledge / RAG gate checklist (pre-release)

**Toolkit:** Prescriptive AI Operator Toolkit  
**Author:** Sidharth Gopakumar  
**Status:** Gate checklist · v0.2 Sep 17, 2026 · Draft v0.2 · for practitioners

---

## Before you call it production

### Silent failure
- [ ] Citations on by default  
- [ ] Abstain when retrieval is thin  
- [ ] Wrong-but-plausible answers measured as a first-class quality metric  
- [ ] Fallback behavior obvious to the operator  

### Grounding surface
- [ ] Documents retrieved shown  
- [ ] Freshness shown next to citations  
- [ ] Permission / tenancy scope reflected in the candidate set (not post-hoc)  
- [ ] Missing evidence that would change the answer is stated  

### Eval harness (pre + post release)
- [ ] Did we retrieve the governing document?  
- [ ] Did we abstain when we should have?  
- [ ] Did permissions change the answer correctly?  
- [ ] Did a document update meet the freshness SLA?  
- [ ] Near-miss cases included (similar keywords, different governing rule)?  

### Priority order (refuse to invert)
1. Index refresh + document lifecycle  
2. Access control + tenancy tests  
3. Silent-wrong eval harness  
4. Operator UX for abstain / escalate  
5. Model or prompt novelty  

### Happy-path trap test
Take the demo question, then: change one document · revoke one permission · delay one feed.  
If the answer stays fluent and wrong → do not ship.

---

## Worked example (enterprise knowledge assist)

| Gate | Pass example | Fail example |
|------|--------------|--------------|
| Citations | Each claim ties to doc id + section | Fluent answer, no trail |
| Abstain | "Insufficient grounding · open ticket / ask human" | Guesses when top-k scores are flat |
| Tenancy | Retrieval filtered before ranking | Filter after generation |
| Freshness | Doc updated yesterday · shown as-of | Stale policy used as current |
| Eval | Nightly suite includes "revoked access" case | Only happy-path golden questions |

**Ship rule:** If any of Silent failure / Tenancy / Happy-path trap fails, hold release. Do not fix with a longer system prompt alone.

---

**Related:** Module 2 Decision object (knowledge feeds the object · does not replace it) · Module 3 Trust contract
