| Capability | Status | Evidence |
|---|---|---|
| Read a file | Observed working | The interface showed **Read clue.txt**, and Hermes returned the exact clue. |
| Write a file | Observed working | The interface showed a **Write** event and diff, and you confirmed the receipt on disk. |
| Retrieve a web page | Not yet verified | Hermes reported `web.run (open)` and returned the expected page details. No retrieval event appeared, even on the verbose retry.
