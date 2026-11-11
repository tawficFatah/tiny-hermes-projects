# Tiny Hermes Projects

Tiny Hermes Projects is a collection of short, hands-on exercises for learning [Hermes Agent](https://github.com/NousResearch/hermes-agent). Each exercise gives you a task, asks you to verify what Hermes actually did, and includes a separate worked solution you can read after your attempt.

The writing style was inspired by Ken Youens-Clark's [*Tiny Python Projects*](https://www.manning.com/books/tiny-python-projects), published by Manning. The exercise text, examples, and solutions were written independently for this project.

## Before you start

You’ll need a working Hermes installation, a configured model that responds in chat, and a checkout of this repository on the machine where Hermes runs. That can be your local Linux or WSL2 environment, or a VPS you connect to remotely. The beginner exercises assume setup is complete. We’ll decide later whether to add installation and setup exercises.

If you need setup material, the Hermes setup used for these exercises is based on Module 2 of [AI Agent Builders on Skool](https://www.skool.com/ai-agent-builders).

## Beginner exercises

| Exercise | What you’ll practice |
| --- | --- |
| [H01 — Meet Your Agent](exercises/beginner/H01-meet-your-agent.md) | Start Hermes, identify the active model, and compare recall within and across sessions. |
| [H02 — The File Clerk](exercises/beginner/H02-the-file-clerk.md) | Turn notes into a checklist and verify that the source file stayed unchanged. |
| [H03 — The Tool Detective](exercises/beginner/H03-the-tool-detective.md) | Test file and web capabilities and distinguish observed tool activity from what the agent reports. |

Start with H01 and work through the three exercises in order. Read each challenge before opening its [worked solution](solutions/beginner/). Record what you observed, including any behavior you couldn’t verify.

## What comes next

The beginner section has three exercises. Intermediate, advanced, and expert material will be developed and reviewed one section at a time.

## Keeping your own exercise notes

Fork this repository on GitHub and use your fork to keep your own exercise notes. Include the exercise ID, the Hermes version you tested, what you observed, and where you got stuck. Commit the notes you want to keep as a record of your progress.

To follow new exercises as they are published, click **Watch** on the [original Tiny Hermes Projects repository](https://github.com/tawficFatah/tiny-hermes-projects) and choose the notifications you want.

If you work on a VPS and keep a local copy, use the [Git workflow guide](GIT-WORKFLOW.md) to compare branches and commits, then sync the two checkouts.
