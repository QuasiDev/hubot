---
permalink: /docs/deploying/windows/index.html
layout: docs
---

Hasn't been fully tested - YMMV

There are 4 primary things to deploying and running hubot in Windows Server:

  * node and npm
  * coffee-script
  * a way to get source code updated on the server
  * a way to start hubot, start it up if it crashes, and restart it when code
    updates

## node and npm

To start, your windows server will need node and npm. 
The best way to do this is with [chocolatey](http://chocolatey.org) using the [nodejs.install](http://chocolatey.org/packages/nodejs.install) package.
I've found that sometimes the system path variable is not correctly set; ensure you can run node/npm from the command line. If needed, set the PATH variable in an elevated command prompt with `set PATH=%PATH%;C:\Program Files\nodejs\`

An alternative way of installing node and npm is to download the Windows installer directly from https://nodejs.org/ and go through the Node.js setup wizard. One thing to make sure is to include "Add to PATH" as an installed feature. This will add Node, npm and modules gloablly installed by npm to the PATH environment variable.

## coffee-script
To install the latest version of coffee-script, perform the following;
1. Open an elevated Command Prompt
2. Run `npm install -g coffee-script`
3. Run `set PATH=%PATH%;%APPDATA%\npm`

## Updating code on the server

The simplest way to update your hubot's code is going to be to have a git
checkout of your hubot's source code (that you've created during [Getting Started](../README.md), not the [github/hubot repository](http://github.com/github/hubot), and just git pull to get change. This may
feel a dirty hack, but it works when you are starting out.

## Starting, stopping, and restarting hubot

Every hubot install has a `bin/hubot` script to handle starting up the hubot.
You can run this command from your git checkout on the server, but there are some problems you can encounter:

* you disconnect, and hubot dies
* hubot dies, for any reason, and doesn't start again
* it doesn't start up at boot automatically

## Expanding the documentation

Not yet fleshed out. [Help contribute by submitting a pull request, please?](https://github.com/github/hubot/pull/new/master)
