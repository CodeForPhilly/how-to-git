# How to Git

## Overview

This is a guide on how to get started using `git` version control software to more easily manage your code and collaborate with other developers.

This guide will really only cover the basics of using `git` with GitHub, since that is where a lot of work and collaboration is happening at the time of writing this.

## The guides

01. [Basics](./guides/01-basics.md)

## Following along

This guide is made for using `git` in the command line, so is meant for using in the Terminal applications in MacOS and Linux or for Windows users, WSL or Powershell. For developers using a code editor like VS Code, those programs come with a terminal application built in.

For those new to it, the command line can be intimidating, but is a powerful tool for looking through your machine, keeping track of changes, and using a variety of command line interface (CLI) tools! Learning the command line will make you a more powerful dev and computer user.

For ease I have included a (WIP) [glossary](./glossary.md) for readers to refer to when necessary.

## What is git for?

From `git`'s own [website](https://git-scm.com/): Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

`git` keeps a log of commits. Each commit is a list of changes to files, a unique ID called a [SHA](https://en.wikipedia.org/wiki/Secure_Hash_Algorithms), and a message that the developer wrote to describe those changes. Commits are often compared to save points in a video game.

Any developer using `git` can use different commands and tools to then keep track of what they've changed over time, go back to a previous state, or add in other developers' changes.

`git` also allows developers to branch off from the current state to make changes without affecting collaborators' code (or the production code!). These branches can later be merged into the main branch once reviewed by peers.