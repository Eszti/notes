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

git config --global pull.rebase true # always pull with rebase (do not create extra merge commit when merging into your local branch)
git config --global core.editor "vim" # use vim instead of nano

grv # (with oh-my-zsh) list remotes
```

### Diff

JSON diff:

```sh
#!/bin/bash

vimdiff <(jq --sort-keys . $1) <(jq --sort-keys . $2)
```

Put this to `~/.local/bin/jqdiff ` and call as `git difftool -x jqdiff main eszti/dev`.


## Troubleshooting

```bash
# Restore after hard reset
git reflog  # find commit
git reset <commit_hash> # resets commit
```

## Tools

- [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
  - info about branch status in command line
- [binder](https://mybinder.org/) 
  - to create online interactive notebooks for a git repository

### Monorepo

- [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)
- [lerna/version](https://github.com/lerna/lerna/tree/main/commands/version)

### Formatting

- [husky](https://github.com/typicode/husky) 
  - for commit hooks
  - needs npm/yarn
- [commitlint](https://commitlint.js.org/#/)

## GitHub

- [Gist](https://gist.github.com/)
  - to instantly share code, notes & snippets