# Tools

## IntelliJ

- Plugins/extra tools
  - update: [JenBeans Toolbox](https://www.jetbrains.com/toolbox-app/)
  - key promoter x plugin
- Important hotkeys
  - alt+shift+left_arrow: navigate back
  - alt+J: multiple cursor (ctrl+ahift+alt+j: all)
  - shift+alt+Ins: Column Selection Mode
    - shift+up/down: multiple cursors
    - mark with mouse
  - ctrl+E: recent files
- Important features
  - zen & presentation mode
- Solved issues
  - broken markdown (javaFX error)
    - choose another java runtime for the IDE
    - [Choose Runtime plugin](https://plugins.jetbrains.com/plugin/12836-choose-runtime)
    - working version: /home/eszter/.sdkman/candidates/java/jdk1.8.0_212
    - mouse selects text autmatically: touch screen problem, touch screen -> works again
- Important plugins
  - [GitToolBox](https://plugins.jetbrains.com/plugin/7499-gittoolbox)
  - [Key Promoter X](https://plugins.jetbrains.com/plugin/9792-key-promoter-x)
  - [Eclipser](https://plugins.jetbrains.com/plugin/7153-eclipser)

## Atlassian

- ? : open shortcuts
- g + g: quick search
- Jira: bulk change: search: tools -> bulk change: edit, change label...
- [Jira rest API](https://developer.atlassian.com/server/jira/platform/rest-apis/)

## git

- configs: local, global (all repos), system (all users)

```bash
git config credential.helper store # unencypted, protected only by file permissions

git push <remote_name> :<branch_name> # delete remote branch

git update-index --skip-worktree FILE # ignore locally
git update-index --no-skip-worktree FILE # do not ignore

git remote -v  # find out origin
git remote set-url origin ORIGIN # set origin
```

- [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
- [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)

## Collaboration Tools

- Miro
- Mural
