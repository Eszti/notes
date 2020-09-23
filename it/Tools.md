# Tools

## Code Quelity

- [SonarCloud](https://sonarcloud.io/)
  - bugs, vulnerabilities, coverae...

## Profiling

- [Apache JMeter](https://jmeter.apache.org/)
  - load testing tool
- [Visual VM](https://visualvm.github.io/)
  - get detailed info about Java applications running on a JVM

## Editors

- [Brackets](http://brackets.io/): web develoopment
- [atom](https://atom.io/)
- [sublime](https://www.sublimetext.com/)

## IntelliJ

### Important hotkeys

- navigate back/forward
  - [alt+shift+left/right]
  - mouse side buttons
- multiple cursor
  - [alt+j] same selections
  - [ctrl+ahift+alt+j] all selection
  - [double-ctrl-keep-pushing-up&down] up & down
- Column Selection Mode
  - [shift+alt+Ins] enter mode
  - multiple cursors
    - shift+up/down
    - mark with mouse
- recent files
  - [Ctrl+E]
- Highlight Usages in File
  - [Ctrl+Shift+F7] highlight all usages
  - [F3/Ctrl+F3] navigate

### Important features

- zen & presentation mode

### Solved issues
  
- broken markdown (javaFX error)
  - choose another java runtime for the IDE
  - [Choose Runtime plugin](https://plugins.jetbrains.com/plugin/12836-choose-runtime)
  - working version: /home/eszter/.sdkman/candidates/java/jdk1.8.0_212
  - mouse selects text autmatically: touch screen problem, touch screen -> works again

### Important plugins & extra tools

- [JenBeans Toolbox](https://www.jetbrains.com/toolbox-app/)
- [GitToolBox](https://plugins.jetbrains.com/plugin/7499-gittoolbox)
- [Key Promoter X](https://plugins.jetbrains.com/plugin/9792-key-promoter-x)
- [Eclipser](https://plugins.jetbrains.com/plugin/7153-eclipser)
- [Code Together](https://plugins.jetbrains.com/plugin/14225-codetogether)
- [String Manipulation](https://plugins.jetbrains.com/plugin/2162-string-manipulation/)
- [GitLink](https://plugins.jetbrains.com/plugin/8183-gitlink)

## Linux

- [autojump](https://github.com/wting/autojump): instead of aliases
- Terminator
- KeePassXC
- Shutter
- [fuzzy finder](https://github.com/junegunn/fzf)
  - Ctrl+R shows more results

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
git push -u origin HEAD # push new branch & set origin

git update-index --skip-worktree FILE # ignore locally
git update-index --no-skip-worktree FILE # do not ignore

git remote -v  # find out origin
git remote set-url origin ORIGIN # set origin
```

- [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
- [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)

## Collaboration Tools

- whiteboards
  - Miro
  - Mural
- drawing
  - [excalidraw](https://excalidraw.com/)
- UML
  - IntelliJ: AsciiDox plugin [plantuml]
  - [PlatText](https://www.planttext.com/)

## Project Management Tools

- [YouTrack](https://www.jetbrains.com/youtrack/?gclid=CjwKCAjwps75BRAcEiwAEiACMZrOZKN3r-n5sJOAKgFoa1jzhw3hzm0Gxz3lPHcEUuIiiBN2923J-hoCnKcQAvD_BwE): from JetBeans

## Security

- [KeePassXC](https://keepassxc.org/): password manager
  - settings: Auto-Type (global hotkey)
  - same password for multiple sites
  - [custom Auto-Type sequence](https://github.com/keepassxreboot/keepassxc/wiki/Autotype-Custom-Sequence)
