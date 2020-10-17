# TIL 2020.10.17
---

### Situation
- Shoot! You have commited wrong commit for opensource community!
- You have commited right commit, but git commit message doesn't look so right!
- ...Or any other bad situation could happen when you are committing.

### Solution
- First, you must push to your origin branch
- `$ git rebase -i HEAD~N`
    - Put number to `N`: `N` commit list will show up so you can fix
- You will see list of commits in format below:
    - [op code] [commit hash] [commit title]
        - e.g. pick e2cffee feat: Add TIL 2020.09.25
- You can change [op code], or change order of the commits
- The lists of 5 op codes that you will mostly use:
    - pick : use commit (leave it as it is)
    - reword: use commit, but edit the commit message
    - squash = use commit, but meld into previous commit
    - fixup  = like `squash`, but discard this commit's log message
    - drop = remove commit