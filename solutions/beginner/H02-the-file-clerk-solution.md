# H02 — Suggested solution

Try the exercise before reading this file.

## Suggested request

Replace `/path/to/tiny-hermes-projects` below with the repository path shown by `pwd` on the machine running Hermes.

> Read `/path/to/tiny-hermes-projects/practice/h02/inbox.md`. Create `/path/to/tiny-hermes-projects/practice/h02/tasks.md` as a Markdown checklist with one item for each distinct task, removing duplicates. Keep all tasks, owners, and due-day wording, including the unanswered launch question. Mark missing owners and dates as unspecified. Leave the source unchanged. If you cannot access the file, explain the limitation. Report the path you created and any uncertainty.

## One acceptable result

```markdown
# Launch tasks

- [ ] Draft welcome message — Owner: Maya; Due: Friday.
- [ ] Check the signup link — Owner: unspecified; Due: unspecified.
- [ ] Choose a banner image — Owner: Leo; Due: Thursday.
- [ ] Ask whether the launch is public or invitation-only — Owner: unspecified; Due: unspecified.
```

Other formatting is fine if it passes every acceptance check. “Thursday” and “Friday” should remain day names because no calendar date was supplied.

## Verification

Open the destination file yourself and compare the source against the starter text. A message saying “saved” is not enough evidence that a file exists or is correct.

If something is missing, ask for a targeted correction, for example: “The launch question is missing. Add it with unspecified owner and due date, keeping the other three items and the source file unchanged.” Then inspect again.

## Verified example

In the November 8, 2026 VPS run, Hermes produced four checklist items, preserved the assigned owners and due days, marked missing details as unspecified, and kept the unanswered launch question. It also added source line references on its own. Those references were optional and the checklist met the acceptance criteria with them included.

The learner opened `tasks.md` and confirmed that `inbox.md` remained unchanged. The run used a repository checkout on the VPS where Hermes was installed. The revised exercise uses full paths so the agent can locate the files from its configured working directory.
