# Tools

## Code Quelity

- [SonarCloud](https://sonarcloud.io/)
  - bugs, vulnerabilities, coverage...

## Profiling

- [Apache JMeter](https://jmeter.apache.org/)
  - load testing tool
- [Visual VM](https://visualvm.github.io/)
  - get detailed info about Java applications running on a JVM

## Editors

- [Brackets](http://brackets.io/): web develoopment
- [atom](https://atom.io/)
- [sublime](https://www.sublimetext.com/)

### Sublime Text

- cheat sheet
  - Ctrl+Shift+D: duplicate line
  - Ctrl+Shift+K: delete line
  - Ctrl+D: select next occurence
  - Ctrl + click: multiple cursors

### IntelliJ

#### Important hotkeys

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

#### Important features

- zen & presentation mode
- semantic highlighting: Editor -> Code Scheme -> Language Defaults -> semantic highlighting

#### Solved issues
  
- broken markdown (javaFX error)
  - choose another java runtime for the IDE
    - [Choose Runtime plugin](https://plugins.jetbrains.com/plugin/12836-choose-runtime)
    - or modify ~/.config/JetBrains/IntelliJIdea2020.3/idea.jdk manually
  - working version: /home/eszter/.sdkman/candidates/java/jdk1.8.0_212
  - mouse selects text autmatically: touch screen problem, touch screen -> works again
- DO NOT INSTALL requiremnts plugin for python !!!

#### Important plugins & extra tools

- [JenBeans Toolbox](https://www.jetbrains.com/toolbox-app/)
- [Key Promoter X](https://plugins.jetbrains.com/plugin/9792-key-promoter-x)
- [String Manipulation](https://plugins.jetbrains.com/plugin/2162-string-manipulation/)

Design
- [Atom Material Icons](https://plugins.jetbrains.com/plugin/10044-atom-material-icons)

Git
- [GitToolBox](https://plugins.jetbrains.com/plugin/7499-gittoolbox)
- [GitLink](https://plugins.jetbrains.com/plugin/8183-gitlink)


Collaborative
- [Code Together](https://plugins.jetbrains.com/plugin/14225-codetogether)
- [Code With Me](https://plugins.jetbrains.com/plugin/14896-code-with-me)

## Linux

- [autojump](https://github.com/wting/autojump): instead of aliases
- Terminator
- Shutter
- [fuzzy finder](https://github.com/junegunn/fzf)
  - Ctrl+R shows more results

## Atlassian

- ? : open shortcuts
- g + g: quick search
- Jira: bulk change: search: tools -> bulk change: edit, change label...
- [Jira rest API](https://developer.atlassian.com/server/jira/platform/rest-apis/)

## git

### General

- configs: local, global (all repos), system (all users)

### Commands

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

### Tools

- [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
- [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)
- [husky](https://github.com/typicode/husky) for commit hooks
- [binder](https://mybinder.org/) online interactive notebooks

## Collaboration Tools

- whiteboards
  - Miro
  - Mural
- drawing
  - [excalidraw](https://excalidraw.com/)
- UML
  - IntelliJ: AsciiDoc plugin [plantuml]
  - [PlantText](https://www.planttext.com/)

## Project Management Tools

- [YouTrack](https://www.jetbrains.com/youtrack/?gclid=CjwKCAjwps75BRAcEiwAEiACMZrOZKN3r-n5sJOAKgFoa1jzhw3hzm0Gxz3lPHcEUuIiiBN2923J-hoCnKcQAvD_BwE): from JetBeans
- [Airtable](https://airtable.com/): also for sheets, calendar and so on

## Security

- [KeePassXC](https://keepassxc.org/): password manager
  - settings: Auto-Type (global hotkey)
  - same password for multiple sites
  - [custom Auto-Type sequence](https://github.com/keepassxreboot/keepassxc/wiki/Autotype-Custom-Sequence)

## Spell checker

- [Grammarly](https://www.grammarly.com/)
  - grammar checker
  - plagiarism
  - various settings like audience, formality, domain, tone, intent
  - only English
- [LanguageTool](https://languagetool.org/)
  - sends encrypted
  - also for German and other languages

## Visualisation

- [Tableau](https://www.tableau.com/)
- [excalidraw](https://excalidraw.com/)
