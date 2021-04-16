# Git

## General

- configs: local, global (all repos), system (all users)
- [how to write a good commit message](https://chris.beams.io/posts/git-commit/)

## Tutorials

- [Oh My Git](https://ohmygit.org/)
- [Git Exercises](https://gitexercises.fracz.com/)

## Commands

```bash
git config credential.helper store # unencypted, protected only by file permissions

git push <remote_name> :<branch_name> # delete remote branch
git push -u origin HEAD # push new branch & set origin

git update-index --skip-worktree FILE # ignore locally
git update-index --no-skip-worktree FILE # do not ignore
git ls-files -v . | grep ^S # list ignored files

git remote -v  # find out origin
git remote set-url origin ORIGIN # set origin

git config --get-regexp alias # list aliases
git config --global alias.co checkout # set alias
```

## Tools

- [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
  - info about branch status in command line
- [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)
- [husky](https://github.com/typicode/husky) 
  - for commit hooks
  - needs npm/yarn
- [binder](https://mybinder.org/) 
  - to create online interactive notebooks for a git repository
- [commitlint]()