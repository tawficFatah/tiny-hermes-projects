# H02 — The File Clerk

**Time box:** 35–45 minutes  
**Level:** Beginner  
**Goal:** Give Hermes a small file task, then check its work yourself.

## Your challenge

Turn a messy set of notes into a useful Markdown task list. Hermes should read a source file, create a new file, and preserve the source exactly.

Use a terminal on the machine where Hermes runs. If Hermes is on a VPS, connect to that VPS and use a checkout of the exercise repository there. If Hermes runs in WSL2 or another local Linux environment, use the checkout in that environment.

## Prepare the case

From the machine running Hermes, enter your repository checkout and create the practice directory. If you cloned it elsewhere, substitute your checkout's path:

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

Start an interactive conversation with `hermes chat`. Write your own request and include the full paths to `practice/h02/inbox.md` and `practice/h02/tasks.md` inside your checkout. Run `pwd` from the repository root to get the directory prefix. For example, if `pwd` prints `/home/hermes/projects/tiny-hermes-projects`, the source path is `/home/hermes/projects/tiny-hermes-projects/practice/h02/inbox.md`.

Include these requirements:

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

For a suggested prompt and example output, open `solutions/beginner/H02-the-file-clerk-solution.md` from the repository root after attempting the challenge.
