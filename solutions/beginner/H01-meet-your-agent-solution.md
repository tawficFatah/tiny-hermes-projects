# H01 — Meet Your Agent: Worked Solution

This example records a learner's run on a VPS using Hermes Agent **v0.23.0 stable**. Try the exercise before reading the worked example.

| Check | Command or action | Observation |
| --- | --- | --- |
| CLI available | `hermes --help` | Hermes listed its commands and options. |
| Interactive chat started | `hermes chat` | Hermes opened an interactive conversation. |
| Model and provider identified | `hermes config` and the chat status line | Configuration showed default model `gpt-6.1-sol` and provider `openai-codex`. The chat status line displayed `gpt-6.1-sol`. |
| Same-session recall | Introduced **Copper Lantern** as a fictional codename, asked an unrelated question, then asked for the codename. | Hermes answered “Copper Lantern.” |
| Fresh-session behavior | Entered `/new` and asked for the codename without repeating it. | Hermes answered “Which project are you referring to?” The learner recorded the `/new` command as evidence of the session boundary. |

## Conclusion

Hermes recalled the invented codename after an intervening question in the original conversation. After `/new`, it asked for project context. These observations show how recall differed between the two conversations in this run and leave persistent memory settings undetermined.
