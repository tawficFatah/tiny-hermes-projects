# H02 — The File Clerk

**Time box:** 35–45 minutes  
**Level:** Beginner  
**Goal:** Give Hermes a small file task, then check its work yourself.

## Your challenge

Turn a messy set of notes into a useful Markdown task list. Hermes should read a source file, create a new file, and preserve the source exactly.

Use your existing Hermes setup in WSL2. No VS Code agent or new installation is needed. The Windows folder `C:\TinyHermesProjects` holds these exercise instructions; do the practice work inside your existing WSL2 repository, `~/projects/tiny-hermes-projects`.

## Prepare the case

In your WSL2 terminal, run:

```bash
cd ~/projects/tiny-hermes-projects
mkdir -p practice/h02
```

Using your usual text editor, create `practice/h02/inbox.md` with this content:

```text
Tiny launch notes
- Maya: draft welcome message, due Friday
- Need to check the signup link; nobody assigned yet
- Leo: choose a banner image, due Thursday
- Maya: draft welcome message, due Friday
- Ask whether the launch is public or invitation-only
- Leo: choose a banner image, due Thursday
```

## Give Hermes the job

Write your own request. Include the source path and destination path, `practice/h02/tasks.md`, plus these requirements:

- Read the source file before producing the result.
- Create a Markdown checklist with one item per distinct task.
- Keep every task, including the unanswered launch question.
- Preserve owners and due-day wording; label missing owners or dates as unspecified.
- Remove duplicate tasks.
- Leave the original file unchanged.
- Report the file created and any uncertainty.

Do not supply the finished checklist yourself. Your job is to specify the outcome clearly enough for Hermes to do the work.

If Hermes cannot access files in this session, stop and note that limitation. Ask it which file capabilities are actually available before trying again in a file-enabled session.

## Inspect the result

Open both files yourself. Check the saved file, not just Hermes's final message.

- [ ] `tasks.md` exists in `practice/h02`.
- [ ] It contains four distinct checklist items.
- [ ] Maya and Leo retain their correct tasks and due days.
- [ ] The signup-link task and launch question both remain.
- [ ] No owner, date, or answer was invented.
- [ ] `inbox.md` is unchanged.

If a check fails, give Hermes one focused correction and inspect the files again.

## Finish

Write two sentences: What did Hermes do well? What did you have to verify yourself?

**Stop after 45 minutes.** A clearly recorded limitation counts as useful progress.

For a suggested prompt and expected output, open `solutions/H02-the-file-clerk-solution.md` after attempting the challenge.
