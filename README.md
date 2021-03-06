# Recent files fuzzy finder Atom package

Quickly find recently opened files through the default [Fuzzy Finder](https://github.com/atom/fuzzy-finder) in [Atom](https://atom.io/).

![demo](https://cloud.githubusercontent.com/assets/978461/6547149/df374dd4-c5cf-11e4-9523-fd892b6ec3e5.gif)

## Why?
The motivation is similar to [navigating to recently opened files](http://blog.jetbrains.com/webide/2013/02/navigating-between-files-in-the-ide-best-practices/) in the [Jetbrains IDEs](https://www.jetbrains.com/).

Personally, I find it more useful to be able to quickly find recently opened files, than having to first check the buffer list and then search the whole project if wasn't already open.

BTW, this plays very well in combination with [zentabs](https://atom.io/packages/zentabs) (_Keep your opened tabs below a maximum limit, closing the oldest one first_), so you don't have to close files manually so the tab bar is actually usable.

## Usage
Open the recent files finder through `alt-T` (i.e. `alt+shift+t`).

Since this plugin basically is an improved buffer list, I  recommend to override the default buffer list shortcut since its more comfortable to use:

```coffee
# ~/.atom/keymap.cson
'atom-workspace':
  'cmd-b': 'recent-files-fuzzy-finder:toggle-finder'
```

You can also clear closed files from the list by calling the command `recent-files-fuzzy-finder:remove-closed-files` (useful when finished on some task and committed changed files).

### Behavior
- The files are listed in order of last usage.
- Current file is excluded from the list.
- The list of recent files is cyclic, i.e. if you have opened more files than the [amount of files to remember](#Configuration) (50 by default) the oldest files will be removed from the list.

## Installation
 `apm install recent-files-fuzzy-finder` in a terminal.

_- or -_

Open Preferences > Packages, and search for `recent-files-fuzzy-finder` package.


## Configuration
These are the configuration values set by default, if you want to you can override them in your own config:

```coffee
# ~/.atom/config.cson
"recent-files-fuzzy-finder":
  maxFilesToRemember: 50
```

## Development

`npm install` and read [CONTRIBUTING.md](CONTRIBUTING.md)
