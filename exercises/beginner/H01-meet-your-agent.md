# H01 — Meet Your Agent

**Level:** Beginner  
**Timebox:** 20–30 minutes (maximum 45 minutes)  
**Environment:** Existing Hermes installation on Linux\
**Status:** Verified on a VPS with Hermes Agent v0.23.0 stable

## The challenge

You have inherited an already-installed Hermes agent. Before assigning it any work, you need to determine how to start it, what model it uses, and whether it remembers information **within a conversation** versus **across a new conversation**.

Your mission: **run a small, repeatable investigation and write down what you actually observe.** Do not change the agent's configuration, install packages, or assume that a fresh session is necessarily memory-free.

## Objectives

By the end, you should be able to:

- Launch Hermes from the terminal and discover available CLI options.
- Identify the model/provider in use, or document why that information is not visible.
- Demonstrate context retention within a single conversation.
- Investigate what changes when you start a fresh session, distinguishing conversation history from persistent memory.
- Record enough evidence for another learner to reproduce your observations.

## Prerequisites

- A working Hermes installation (Level 0 setup exercises will be written later).
- Terminal access to the machine running Hermes.
- A configured model that can answer prompts.
- Permission to start a new, disposable session; **do not reset or delete your existing agent's production data**.

No local model, Telegram, WhatsApp, or Python coding is required.

## Acceptance criteria

Your exercise is complete when you can show all of the following:

1. A terminal command that confirms the Hermes CLI is available.
2. The method you used to open an interactive Hermes conversation.
3. Evidence that the agent recalls a harmless, invented fact later **in the same conversation**.
4. A **new** conversation/session and an observation about whether that fact is available there.
5. A short note identifying the active model/provider (if observable) and the source of that information.
6. A conclusion that distinguishes what you **observed** from what you **inferred** about session history or memory.

**Safety constraint:** Use a made-up token, not a password, API key, personal detail, or business secret.

## Your investigation

### Part A — Discover the interface

From a terminal on the machine with Hermes installed:

- Find a way to display the Hermes CLI's available commands/options.
- Start an interactive conversation.
- Determine where you can inspect the active model/provider without exposing credentials.

Keep a record of the commands or interface actions you used.

### Part B — Test conversation continuity

In one conversation, tell the agent a fictional fact such as:

> For this exercise only, the imaginary project's codename is **Copper Lantern**.

Send at least one unrelated prompt, then ask for the codename. Record whether the agent answers correctly.

### Part C — Test a fresh session

Start a genuinely new conversation/session using the method available in **your installed Hermes version**. Ask for the codename again **without repeating it**.

Record the answer, including uncertainty or a refusal to guess. Do **not** interpret recall as proof that the same chat history was reused: a persistent memory or shared context could also explain it. Likewise, failure to recall does not prove all persistent memory is disabled.

### Part D — Report your findings

Create a short local note (for example, `H01-observations.md`) with:

| Check | Command/action used | Observation | Pass? |
|---|---|---|---|
| CLI available | | | |
| Interactive chat started | | | |
| Model/provider identified or limitation explained | | | |
| Same-session recall | | | |
| Fresh-session behavior recorded | | | |

Finish with **two or three sentences** explaining what you learned about sessions versus persistent memory.

## Verification (manual test)

There is no deterministic automated test in H01: responses and memory configuration vary across installations.

Use this checklist:

- [ ] I can reproduce the CLI launch procedure.
- [ ] I tested recall after an intervening message.
- [ ] I verified that the second test was in a new session.
- [ ] I captured both results without claiming more than the evidence supports.
- [ ] I did not expose secrets or alter existing production data.
- [ ] I finished in 45 minutes or less (or noted where I got stuck).

## Hints — reveal only if needed

<details>
<summary>Hint 1 — Finding commands</summary>

Try the standard command-line help convention on the `hermes` executable. Check the output before guessing subcommands.

</details>

<details>
<summary>Hint 2 — Starting a conversation</summary>

An installation may offer an interactive CLI mode. Look for it in the help output or in the official quickstart for your installed version.

</details>

<details>
<summary>Hint 3 — Fresh sessions</summary>

Leaving and reopening a terminal is not necessarily the same as starting a new Hermes session. Find the documented session control and verify that you are no longer continuing the previous conversation.

</details>

<details>
<summary>Hint 4 — Model identity</summary>

Check any model/status information exposed by the CLI or non-secret configuration. Never paste the contents of `.env`, API keys, or access tokens into your report.

</details>

## Stretch challenge (optional, 5 minutes)

Repeat Part C with a *second* fictional fact. Does the result match your first observation? Suggest one additional test that would help distinguish persistent memory from session reuse.

## Debrief

- What evidence convinced you that you were in a new session?
- Which behavior was controlled by Hermes, and which may have been controlled by model or memory configuration?
- What would you change in this exercise to make it easier for someone using a different provider or a VPS?

## References

- [Nous Research Hermes Agent — official repository](https://github.com/NousResearch/hermes-agent)
- [Hermes quickstart (official repository)](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/getting-started/quickstart.md)

**Curriculum coverage:** CLI discovery; interactive conversations; model identification; session boundaries; introductory memory observations.  
**Reference solution:** Kept separately in `solutions/` and intentionally not included here.
