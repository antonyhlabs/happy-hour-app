# Happy hour app (working name)

Singapore-first, crowd-mapped happy hour app. Beer first.

**This repo is the source of truth for the plan.**

| File | What it is |
| --- | --- |
| `plan.md` | The current agreed plan |
| `decisions.md` | Every agreed decision, dated, with its source |
| `comments-v1.md` | Ant's comments on plan v1, word for word |

How changes happen:
1. Ideas and debate happen in the working doc on claude.ai (comments).
2. Once Ant agrees, the change is made here in one commit, with a note saying what changed and why.
3. Each agreed round is tagged (`v1`, `v2`, ...). Use `git diff v1 v2 -- plan.md` to see what changed.
