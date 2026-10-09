# <Project name>

<One or two lines: what this project is and who uses it. Fill in when you copy this boilerplate.>

## Commands

Fill these in. Agents run them without asking.

- Install: `<command>`
- Run locally: `<command>`
- Test: `<command>`
- Lint, format, and typecheck: `<command>`

Docs live in `<path>`. Start there before answering questions about the project.

## How to work

- Real engineering work (a bug, a feature, a refactor, an investigation, a long run) starts with the `saiyan` skill. It picks a playbook and applies the principals.
- Work big enough for a written plan or several PRs: `task-create` writes the plan, `task-execute` runs it, and `task-progress` records decisions and what's left.
- Do not use any of them for questions, discussion, or one-off small edits.
- Before saying done, verify on the real thing with this project's `verify-*` skill. If the project has none, run `verify-create` first. "It compiles" is not verification.
- `.agents/metl/tasks.md` is the mission essential task list: what must always work. Check your change does not break any of it, and keep it current.
- Reproduce a bug before fixing it, and verify on the same surface.

## Git

- Work on a branch named for the task. Do not commit to `main` unless asked.
- Commit small, ordered changes with messages in this repo's style.
- Stage explicit paths. Never `git add -A`, because other agents may share the tree.
- Never force-push a shared branch, merge, or deploy unless asked.
- Only push when the user asks you to.

## Always pause for

Irreversible actions: deploys, deleting data, force-pushes, messages to customers, spending money. Everything reversible, just do it.

## Secrets

Never commit secrets and never print them in replies or logs. Name the environment variable or secret store instead.

## Keeping this file useful

Every agent reads this file every session, so keep it short. If you correct the same mistake twice, fix it in structure (a script, a lint rule, a check) rather than adding a paragraph here. Setup details such as symlinks and where tools read config are in `README.md`.
