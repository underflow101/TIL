# TIL 2020.10.28
---

### git reset --hard

- `$ git reset` has 3 options, but today's learning is about how to use `$ git reset` in real field.
- When HEAD is pointing to somewhere old, you can either merge from upstream or fetch it.
- But if you want to make your branch clean, and also make your branch exactly same with upstream's master branch, you can use `$ git reset` as following:
    1. `$ git fetch upstream`
    2. `$ git reset --hard upstream/master`
- This operation will wipe out your current branch's work; so if you want to save current status, you must make another branch, or save your work manually.