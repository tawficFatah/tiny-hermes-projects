# H03 — The Tool Detective

**Time box:** 30–40 minutes  
**Level:** Beginner  
**Goal:** Distinguish what Hermes says it can do from what you can observe it doing.

## Your challenge

Investigate three capabilities in your current Hermes session:

1. Reading a local file.
2. Writing a local file.
3. Retrieving information from the web.

For each capability, decide whether it is **observed working**, **reported unavailable**, or **not yet verified**. Tool availability depends on your session; you do not need all three capabilities to pass.

Use your existing Hermes setup. No new VS Code agent, software installation, or configuration change is part of this exercise.

## Prepare a private test clue

In your WSL2 terminal, run:

```bash
cd ~/projects/tiny-hermes-projects
mkdir -p practice/h03
```

Using your usual editor, create `practice/h03/clue.txt`. Put a short, harmless phrase of your choice inside it. Keep the phrase out of your Hermes prompt so that reading the file is necessary to discover it. Do not use passwords or personal information.

## Investigate

First ask Hermes which relevant tools are available in this session. Ask it to distinguish actual available tools from capabilities it is merely describing.

Then devise one small test for each capability:

- **Read:** Ask Hermes to read `practice/h03/clue.txt` and report the phrase. Compare its answer with the file.
- **Write:** Ask Hermes to create `practice/h03/receipt.md` containing a short receipt for the clue it read. Open the saved file yourself.
- **Web:** Ask Hermes to retrieve `https://example.com`, report the page title, and identify the tool used. Look for an actual tool invocation or retrieval result. Knowing the page title from memory does not demonstrate retrieval.

When tool activity is visible, record the tool name exactly as displayed. When it is hidden, say so. Do not invent a tool name or treat a confident answer as proof.

If a capability is unavailable, record that result and continue. Do not install or enable anything just to complete this exercise.

## Record the evidence

Create `practice/h03/findings.md` yourself, using this table:

| Capability | Status | Evidence | Limitation or uncertainty |
| --- | --- | --- | --- |
| Read a file | | | |
| Write a file | | | |
| Retrieve a web page | | | |

Use only these status labels: **observed working**, **reported unavailable**, **not yet verified**.

## Acceptance checks

- [ ] Each capability has a status and a concrete observation.
- [ ] The read test used a phrase absent from your prompt.
- [ ] You inspected the receipt on disk before marking writing as working.
- [ ] The web result distinguishes retrieval evidence from prior knowledge.
- [ ] Any invisible tool activity or missing evidence is stated clearly.
- [ ] You made no installation or configuration changes.

## Finish

Answer: “What evidence would make me trust the next file or web task?”

**Stop after 40 minutes.** Missing capabilities are findings, not failures.

For suggested requests and an evidence guide, open `solutions/H03-the-tool-detective-solution.md` after attempting the challenge.
