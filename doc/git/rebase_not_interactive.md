# TIL 2020.09.05
---

### Situation
- Sometime a trouble occurs when you are contributing to open source like:
    - You have created a PR(Pull Request) and the CI/CD system build fails
    - But it's not your fault! Something needs to be fixed prior to your source
    - Then someone who is in charge of that source code fixes that code, and then asks you to rebase your PR
    - Without closing & re-opening your PR, how can you put your commits after the fix of that code that is not yours?

### Solution
- `$ git fetch upstream master`
- `$ git rebase upstream/master`
- `$ git push origin/your_PR_branch`
    - if this doesn't work, use:
        - `$ git push --force origin/your_PR_branch`
- Now problem is gone! Your whole commits in PR will be placed right after the fix of that code