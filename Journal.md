## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/153

**Issue title:** Faithfulness checker crashes when a context chunk has text: None

**Tier:** [*] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The issue is faithfulness checker builds context from text from chunks and it currently uses chunk.get("text",""), but if the chunk contains "text": None the .get() call returns None and "".join() raises a type error. It crashes on valid chunk structures that include None values instead of text. The fix would be to normalize None to an emptu string before joing, allowing the checker these chunkks gracefuly and the existing unit test passing.

**Branch name:** fix/153-faithfulness-checker-crashes

**Setup confirmation:** [*] App runs locally at localhost:5173

**Cohort ledger:** [*] Issue added to cohort ledger