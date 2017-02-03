---
layout: post
title: My Visual Studio Code setup
tags: [python, osx, windows, linux]
---

![](https://cloud.githubusercontent.com/assets/994357/20610669/042cc31a-b29d-11e6-9657-87427ceb9e6a.png)

This is my [Visual Studio Code](https://code.visualstudio.com) (vscode) setup, with ambitions to create a custom Python IDE.

I previously posted about my Sublime Text 3 (ST3) setup [here]({{ site.baseurl }}2016/05/20/my-sublime-3-setup/), but I've fully moved on to use vscode instead so I figured I'd share this new setup.

<!--more-->

## The dream setup

I took a weekend and compared ST3 (my then current editor of choice) against vscode and Atom to see which editor suited me best. Basically, my dream is to be able to jump between different machines on different platforms and open up the same editor and have everything "just work" the same way. Some people would bring up Vim, and [I do use it](https://github.com/fredrikaverpil/dotfiles/blob/master/vimrc) although sparingly, as I actually prefer a GUI editor.

So, I was looking to get the following to work "cross-machine" and cross-platform:

* One single user settings configuration to rule them all
  * Custom Python interpreter (+ packages)
  * Global build system/tasks
  * Packages/extensions, themes
* Project settings
  * Custom Python interpreter (+ packages)
  * Build system/task
* Project manager
* Auto-completion / Intellisense
* Integrated terminal
* Integrated git support
* Debugger abilities
* Commited files highlighting
* Trailing spaces detection (and auto-deletion)
* Battery efficiency (commuting with laptop)
* Material-themed editor (I really like this)
* Syntax highlighting for a wide variety of languages
* Minimap
* Go to definition, look up symbols etc
* Command palette

Naturally, not one of the editors (and their packages/extensions) offers all of the above seamlessly and instead you find some of them supporting some features and to different extent.

However, I found vscode to offer the most in this list and having a super active developer community over at Github. Just look at their [iteration plans](https://github.com/Microsoft/vscode/wiki/Iteration-Plans). I find this impressive.

Also, there's a fantastic Python extension jam-packed with features: [pythonVSCode](https://github.com/DonJayamanne/pythonVSCode) by Don Jayamanne.

So after having realized this I wanted to give vscode a try and switched over to it at work. I soon realized vscode had a lot of other extensions I now have trouble living without. You can say I was won over quickly.


## What's missing from the dream setup?

So, there are some functionality I'm still missing which I'm closely tracking via github issues.

Note: strikethrough means features were implemented, either in the [insider build](https://code.visualstudio.com/insiders) of vscode or in the affected extension.

* Git status in file explorer: [vscode#178]( https://github.com/Microsoft/vscode/issues/178)
* Minimap: [vscode#4865](https://github.com/Microsoft/vscode/issues/4865)
* Define Python settings based on variables and overrides: [pythonVSCode#644](https://github.com/DonJayamanne/pythonVSCode/issues/644)
  * ~~Improved support for python settings (auto-detect interpreter): [pythonVSCode#353](https://github.com/DonJayamanne/pythonVSCode/issues/353)~~
  * ~~Support file-type-specific settings: [pythonVSCode#1587](https://github.com/Microsoft/vscode/issues/1587#issuecomment-273397301)~~
  * Create environment variable within user/workspace settings: [vscode#18709](https://github.com/Microsoft/vscode/issues/18709)
  * Support environment variables when resolving values in settings: [vscode#2809](https://github.com/Microsoft/vscode/issues/2809)
  * Add OS-specific dependency PATHs: [vscode#17619](https://github.com/Microsoft/vscode/issues/17619#issuecomment-273424889)
* Automatically expand full docstring when autocompleting: [pythonVSCode#645](https://github.com/DonJayamanne/pythonVSCode/issues/645)
* Disable auto-completion when writing comments/docstrings: [pythonVSCode#74](https://github.com/DonJayamanne/pythonVSCode/issues/74)
* Sync Color Theme Settings: [code-settings-sync#185](https://github.com/shanalikhan/code-settings-sync/issues/185)
* Option to ignore sync some settings, files and folders: [code-settings-sync#100](https://github.com/shanalikhan/code-settings-sync/issues/100)
* Support cross platform path definitions ($HOME) [vscode-project-manager#88](https://github.com/alefragnani/vscode-project-manager/issues/88)

I also wasn't able to find a Material theme which resembled the one I wanted to use, so I created [one](https://marketplace.visualstudio.com/items?itemName=fredrikaverpil.vscode-material-theme). It's identical to the `Material-Theme.tmTheme` by [Mattia Astorino](https://github.com/equinusocio) which I used to have in ST3. There are talks about opening up the UI API ([vscode#1833](https://github.com/Microsoft/vscode/issues/1833)) to allow for the kind of UI customization Mattia has been doing with ST3 and it seems like he might be [looking to use that](https://github.com/equinusocio/vsc-material-theme) when possible, wich would be awesome.

Worth mentioning is that [a lot of work](https://github.com/Microsoft/vscode/pull/17933) was done on the TextMate tokenization in vscode 1.9 which now allows for the Material theme (and others) to render like intended. This work also opens up for a minimap (!).


## My setup (`settings.json`)

There's a nice extension which makes it quite to keep your entire vscode setup in sync with other machines: [Settings sync](https://github.com/shanalikhan/code-settings-sync/). This extension uploads your settings into a private Github gist (using a Github token) which can be updated/downloaded on demand or, if you wish, automatically when the settings change.

I would've wanted to use this to sync my vscode experience between my macOS laptop and my Windows workstation but there are some cross-platform path caveats (Github issues listed above). So for now I need to maintain one gist for macOS and one for Windows.

#### Extensions

These are all extensions I use frequently.


* [Python](https://github.com/DonJayamanne/pythonVSCode) <--- seriously, check this out.
* [Project Manager](https://github.com/alefragnani/vscode-project-manager)
* [Settings Sync](https://github.com/shanalikhan/code-settings-sync)
* [Trailing Spaces](https://github.com/shardulm94/vscode-trailingspaces)
* [Material Theme](https://github.com/fredrikaverpil/vscode-material-theme)
* [Open in Github/Bitbucket](https://github.com/ziyasal/vscode-open-in-github)
* [MayaPort](https://github.com/NCCA/mayaport)
* [MEL - Maya Embedded Language](https://github.com/sator-imaging/Visual-Studio-Code-MEL-Language)
* [Clock in status bar](https://github.com/compulim/vscode-clock)
* [Docker Support](https://github.com/Microsoft/vscode-docker)
* [Jinja](https://github.com/wholroyd/vscode-jinja)
* [Prettify JSON](https://github.com/mohsen1/vscode-prettify-json)
* [gitignore](https://github.com/CodeZombieCH/vscode-gitignore)


#### Python settings

Pyhton-specifics in my `settings.json` (user settings).


```json
{
    // vscode
    "editor.detectIndentation": true,
    "files.insertFinalNewline": true,
    "editor.formatOnPaste": true,

    // only for python language files
    "[python]": {
        "editor.rulers": [72, 79],
        "editor.tabSize": 4,
        "editor.insertSpaces": true
    },

    // pythonVSCode extension
    "python.pythonPath": "/Users/fredrik/miniconda3/envs/dev_py35",
    "python.linting.pylintEnabled": true,
    "python.linting.flake8Enabled": false,
    "python.linting.pep8Enabled": true,
    "python.linting.lintOnTextChange": true,
    "python.formatting.provider": "yapf",
    "python.formatting.yapfArgs": ["--style", "{based_on_style: chromium, indent_width: 4}"]
}
```

Please note how you don't have to specify the full path to the Python binary. This works cross-platform!


#### Other extension settings

```json
{
    // Trailing spaces
    "trailing-spaces.trimOnSave": true,

    // Project manager
    "projectManager.openInNewWindow": false,
    "projectManager.sortList": "Name",
    "projectManager.git.baseFolders": [
        "/Users/fredrik/code/repos",
        "C:/Users/fredrik/code/repos"
    ]

}
```

## Workspace settings vs user settings

You can override your user settings on a per-project (a.k.a workspace) basis. These workspace settings are stored in `your_project/.vscode/settings.json`.

This is great if you e.g. wish to override the Python interpreter (used for debugging, launching tasks etc), disable certain linting warnings or perhaps add additional autocompletion paths:


```json
{
    "python.pythonPath": "${workspaceRoot}/../../../skalman/condaenvs/skalman_py35/",
    "python.linting.pylintArgs": ["--disable=E0611"],
    "python.autoComplete.extraPaths": [
        // Maya 2017, OS X
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python27.zip",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/plat-darwin",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/plat-mac",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/plat-mac/lib-scriptpackages",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/lib-tk",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/lib-old",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/lib-dynload",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/bin",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/Python",
        "/Applications/Autodesk/Maya2017/devkit/other/pymel/extras/completion/py",
        "/Applications/Autodesk/maya2017/Maya.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python2.7/site-packages"

        ]
}
```

You can create tasks which you can invoke with `Tasks: Run tasks` from the command palette. Here's an example `your_project/.vscode/tasks.json` which works in conjunction with the pythonVSCode extension, cross platform!

```json
{
    "version": "0.1.0",
    "echoCommand": true,
    "_runner": "terminal",
    "tasks": [
        {
            "taskName": "Build docs",
            "command": "dummy",
            "osx": {
                "command": "${workspaceRoot}/../../../skalman/condaenvs/skalman_py35/bin/python ${workspaceRoot}/scripts/build_docs/build_docs.py"
            },
            "windows": {
                "command": "${workspaceRoot}/../../../skalman/condaenvs/skalman_py35/Python.exe ${workspaceRoot}/scripts/build_docs/build_docs.py"
            },
            "isShellCommand": true,
            "isBackground": false
        },
        {
            "taskName": "Run My app",
            "command": "dummy",
            "osx": {
                "command": "$HOME/skalman/condaenvs/skalman_py35/bin/python ${workspaceRoot}/scripts/standalone_gui/standalone_gui.py"
            },
            "windows": {
                "command": "%HOMEDRIVE%%HOMEPATH%/skalman/condaenvs/skalman_py35/python.exe ${workspaceRoot}/scripts/standalone_gui/standalone_gui.py"
            },
            "isShellCommand": true,
            "isBackground": false
        }
    ]
}
```

And then we have the debugger. The debugger settings are stored in `your_project/.vscode/launch.json`. Here's a quick example:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "My app",
            "type": "python",
            "request": "launch",
            "stopOnEntry": false,
            "console": "integratedTerminal",
            "pythonPath": "${config.python.pythonPath}",
            "program": "${workspaceRoot}/scripts/standalone_gui/standalone_gui.py",
            "cwd": "${workspaceRoot}",
            "debugOptions": [
                "WaitOnAbnormalExit",
                "WaitOnNormalExit"
            ]
        },
        {
            "name": "Python (opened file)",
            "type": "python",
            "request": "launch",
            "stopOnEntry": true,
            "pythonPath": "${config.python.pythonPath}",
            "program": "${file}",
            "cwd": "${workspaceRoot}",
            "debugOptions": [
                "WaitOnAbnormalExit",
                "WaitOnNormalExit",
                "RedirectOutput"
            ]
        }
    ]
}
```


### What's next?

I like to peek [in here](https://github.com/Microsoft/vscode-docs/tree/vnext/release-notes) to see what's coming up next.