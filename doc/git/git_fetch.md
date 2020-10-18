# TIL 2020.10.18
---

### git fetch
- When you are trying to contribute to open source commnunity, `$ git fetch` can be your great ally
- Also, you will use `$ git fetch` command if you are working on multiple computers
- `$ git fetch` command needs [which remote] to fetch; [which branch] to fetch is optional
    - e.g.) `$ git fetch upstream`
    - e.g.) `$ git fetch upstream master`
- You can also fetch from `origin`: `$ git fetch origin`
- You need this operation, especially working with others in open source community, because you need to catch up with latest commits
    - After `$ git fetch upstream`, `$ git reset --hard upstream/master` usually helps to keep up with latest commit