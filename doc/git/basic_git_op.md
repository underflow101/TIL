# TIL 2020.11.07
---

### Basic git Operations
- When you want to clone your repository from remote:
    - `$ git clone ~~~`
- When you want to add every source codes in your directory:
    - `$ git add .`
    - `$ git commit -s`
    - `$ git push`
- When you want to add specific source code in your directory:
    - `$ git add /dir/to/your/source/code.cpp`
    - `$ git commit -s`
    - `$ git push`
- When you want to update your local repo to your remote repo's status:
    - `$ git pull`
- Or,
    - `$ git fetch origin`
    - `$ git reset --hard origin/master`
- Or,
    - `$ git fetch origin`
    - `$ git merge origin/master`
- When you want to stash your works
    - `$ git stash`
