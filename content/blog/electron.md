---
title: First impressions on Electron
date: 2017-08-05 14:40:04 +0000

---
# First impressions on `electron`

Today I wanted to find an easy way to edit markdown documents, especially on the context of this blog. I thought it could be a nice way to hands on two (not so recent) technologies:

* [Electron](https://electron.atom.io/)
* [Vue.js](https://vuejs.org/)

I was an early adopter of Atom, then switched to Visual Studio Code. This is how I discovered Electron: it is the framework behind these tools (but also HipChat, Slack clients, ...). It allows to create cross platform desktop apps using web technologies.

## First steps

The official website of Electron ([https://electron.atom.io/](https://electron.atom.io/)) contains all the required tutorials to get started with it. Only required dependancies are `npm` and `git`.

```bash
# Clone the quick start repository
git clone https://github.com/electron/electron-quick-start
# Go into the repository
cd electron-quick-start
# Install dependencies
npm install
# Run the app
npm start
```

This provide a basic "hello world!" application, with default menus, and standard events management (start, close, ...).

## Electron starter kits and Electron Forge

### Bootstraping

An other way to bootstrap an application is by using a starter kit. Multiple, sometimes outdated starter kits may be found. The one you choose will probably be defined by the underlying javascript framework that you plan to use (React, Angular, ...).

There is one officially supported tool that allow such choice, it is \[Electron Forge\] (https://electronforge.io/). Usage is as simple as a single call to this npm based tool. Multiple [templates](https://electronforge.io/templates) are available in order to pre-install one of the modern popular javascript framework. As explained above, I choosed Vue.js.

```bash
npm install -g electron-forge
electron-forge init my-new-project --template=vue
```

### Development cycle

The electron forge allow short development cycle. Any change in local files (html, js, vue, ...) is automatically loaded in the started application.

```bash
cd my-new-project
electron-forge start
```

Within the application, Chrome dev tools are here. Console, DOM inspector, js debuger, ... It became as easy as developing a web app to develop a desktop one.

## Key takeaways

* Use  [Electron Forge](https://electronforge.io/) to bootstrap your application
* Integration with Chrome dev tools is great
* Develop a web UI but with all modern JS/CSS allowed (only one browser engine will have to render it)