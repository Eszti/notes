# Tools

## IntelliJ

- Plugins/extra tools
  - update: [JenBeans Toolbox](https://www.jetbrains.com/toolbox-app/)
  - key promoter x plugin
- Important hotkeys
  - alt+shift+left_arrow: navigate back
  - alt+J: multiple cursor
  - ctrl+E: recent files
- Important features
  - zen & presentation mode
- Solved issues
  - broken markdown (javaFX error): choose another java runtime for the IDE (with plugin)
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
git config credential.helper store // unencypted, protected only by file permissions
```

- delete remote branch:

```shell
git push <remote_name> :<branch_name>
```

- ignore locally: git update-index --skip-worktree _file_
- reverse: git update-index --no-skip-worktree _file_
- [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
- [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)
