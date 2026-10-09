# METL: mission essential task list

The short list of things this project must be able to do for it to count as working. If one of these is broken, nothing else matters until it is fixed.

Keep it to roughly five to fifteen tasks. Each is a plain sentence a user would recognise, such as "A new user can sign up and log in" or "A repayment posts to the ledger".

## How agents use it

- Before saying work is done, check that no METL task is broken by the change. Use the matching `verify-*` feature file to prove it.
- When a METL task fails, it outranks whatever else you were doing. Fix it or report it first.
- When you add or remove an essential capability, update this list in the same change.

## Format

Put the list in `tasks.md`, one row per task:

| Task | Why it is essential | Proved by |
| --- | --- | --- |
| A new user can sign up and log in | No access, no product | `verify-<app>/features/login.md` |
