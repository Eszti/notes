# Editors

- [Brackets](http://brackets.io/): web develoopment
- [atom](https://atom.io/)
- [sublime](https://www.sublimetext.com/)

## Sublime Text

- cheat sheet
  - Ctrl+Shift+D: duplicate line
  - Ctrl+Shift+K: delete line
  - Ctrl+D: select next occurence
  - Ctrl + click: multiple cursors

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
- semantic highlighting: Editor -> Code Scheme -> Language Defaults -> semantic highlighting
- Configure issue tracking
  - Tools | Tasks | Servers
  - `Alt+Shift+N`

### Troubleshooting
  
- broken markdown (javaFX error)
  - choose another java runtime for the IDE
    - [Choose Runtime plugin](https://plugins.jetbrains.com/plugin/12836-choose-runtime)
    - or modify ~/.config/JetBrains/IntelliJIdea2020.3/idea.jdk manually
  - working version: /home/eszter/.sdkman/candidates/java/jdk1.8.0_212
  - mouse selects text autmatically: touch screen problem, touch screen -> works again
- DO NOT INSTALL requiremnts plugin for python !!!
- `you aren't using a compiler supported by lombok`
  - invalidate cache or
  - Build,Execution,Deployment -> Compiler -> Shared build process VM options
    - `-Djps.track.ap.dependencies=false` 
    - `-javaagent:/home/eszter/.m2/repository/org/projectlombok/lombok/1.18.16/lombok-1.18.16.jar`: path to local lombok

### Important plugins & tools

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
  - uses browser
- [Code With Me](https://plugins.jetbrains.com/plugin/14896-code-with-me)
  - installs a lightweight client IDE
