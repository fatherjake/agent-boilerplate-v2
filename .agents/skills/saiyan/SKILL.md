---
name: saiyan
description: Front door for engineering work. Use at the start of any real bug fix, feature, refactor, investigation, or long unattended run. Reads the request, picks one playbook, copies its steps into the todo list, and applies the principals. Skip for questions, quick edits, and chat.
---

# Saiyan

Give it a goal and a way to check it. It picks the playbook, runs the steps, and shows the evidence.

## How to run

1. Restate the goal and the check that proves it is done, in one or two lines. If you cannot state a check, say so and propose one.
2. Pick the playbook that matches the request. If none fits, say so and use the closest one.
3. Copy that playbook's steps into the todo list before doing any work. If you skip a step, keep it in the list marked `skip: <reason>`.
4. Do the work. Read a principal when its trigger fires (see below). Do not read them all up front.
5. Before saying done, run `principals/prove-it-works.md`. Reply with what you changed, how you verified it, and anything open.

## Playbooks

| Playbook | Use when |
| --- | --- |
| [bug-fix](playbooks/bug-fix.md) | Something is broken or behaves wrongly. |
| [feature](playbooks/feature.md) | New behavior or a change to existing behavior. |
| [refactor](playbooks/refactor.md) | Same behavior, better structure. |
| [investigation](playbooks/investigation.md) | The goal is to understand, not to change code. |
| [autonomous-run](playbooks/autonomous-run.md) | A long or unattended run toward a checkable exit condition. |
| [ship](playbooks/ship.md) | The change is verified and needs to become a pull request. |

For work big enough to need a written plan or tickets, use the `task-create` skill first, then `task-execute`.

## Principals

Short rules in `principals/`. Read one when its trigger fires.

| Principal | Trigger |
| --- | --- |
| [prove-it-works](principals/prove-it-works.md) | Before declaring any task done. |
| [fix-root-causes](principals/fix-root-causes.md) | Debugging. |
| [test-behavior-not-implementation](principals/test-behavior-not-implementation.md) | Writing or keeping a test. |
| [laziness-protocol](principals/laziness-protocol.md) | Tempted to add a layer, abstraction, or extra code. |
| [subtract-before-you-add](principals/subtract-before-you-add.md) | Sequencing an addition or refactor. |
| [encode-lessons-in-structure](principals/encode-lessons-in-structure.md) | Writing the same instruction twice, or fixing a repeated mistake. |
| [never-block-on-the-human](principals/never-block-on-the-human.md) | About to ask "should I do X?" on reversible work. |
| [type-system-discipline](principals/type-system-discipline.md) | Designing types or reading a function signature. |

Principals are plain files, not skills, so they do not load at startup. Add a new one only after the same mistake shows up twice.

## Ground rules

- Reproduce before fixing. Verify on the same surface you reproduced on.
- Ask only about irreversible actions or product calls no experiment can settle.
- Keep a record of key decisions with the `task-progress` skill on any run longer than one sitting.
