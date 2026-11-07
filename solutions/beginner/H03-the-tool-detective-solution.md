# H03 — Suggested solution

Try the exercise before reading this file.

## Suggested requests

1. “Which tools available in this session can read files, write files, or retrieve a web page? Distinguish available tools from general capabilities. Do not claim a tool is available unless you can identify it from this session.”
2. “Read `practice/h03/clue.txt` in my repository and report its exact contents. If you cannot access it, say so.”
3. “Create `practice/h03/receipt.md` containing the phrase you read and a sentence saying it came from the clue file. Report the saved path.”
4. “Retrieve `https://example.com` now and report its page title and the tool used. If live retrieval is unavailable, say so instead of answering from memory.”

## Evidence guide

| Capability | Evidence for observed working | When evidence is insufficient |
| --- | --- | --- |
| Read | The returned phrase matches the file and was absent from the prompt. | The phrase was already supplied in the conversation. |
| Write | You open the new file on disk and confirm its contents. | Hermes only prints text or says it saved a file. |
| Web | Visible retrieval activity or a retrieval result supports the returned title. | Hermes gives a plausible title without retrieval evidence. |

Use **reported unavailable** when Hermes reports that access is missing. Use **not yet verified** when the claim has not been demonstrated or the evidence is ambiguous. Record failed attempts in the evidence column; a failed attempt alone does not establish that a capability is permanently unavailable.

There is no single correct tool list. Names and capabilities depend on the actual session. Hidden tool activity should be recorded as a limitation, not filled in with a guessed tool name.

## Example reflection

“I will inspect the saved file before trusting a write. For a web task, I will look for retrieval evidence rather than relying on a confident answer.”
