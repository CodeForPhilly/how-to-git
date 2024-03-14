# 01 Basics

## Getting used to the command line

The command line is a text input line where you will put in commands to tell the computer what to do. These commands can be written into documents called scripts. 

### Open the command line

For MacOS and Linux users, open the Terminal application. For Windows users, open WSL or Powershell. Or for any OS, open the terminal tool in VS Code or your code editor of choice.

> For Windows users, these instructions should work for using the terminal tool in VS Code, but is not yet translated for WSL or Powershell. All of the `git` commands will work (commands that start with `git`), but not all of the `bash` commands will. Please look at the documentation for [WSL](https://learn.microsoft.com/en-us/windows/wsl/) and [Powershell](https://learn.microsoft.com/en-us/powershell/).

### Orientation to Bash and shell commands

The command line is a "shell" program that "wraps around" your computers operating system and translates (mostly) human-readable commands into computer-readable assembly code.

It is common to hear these referred to as bash commands referring to the popular `bash` (Bourne Again SHell) shell program that comes natively on many machines. MacOS users will often have `zsh` natively on their machines and for the most part, these are interchangeable. You can choose your own shell programs (the author uses ['oh-my-zsh'](https://ohmyz.sh/) at the time of  writing). The following commands listed here should be available across all of these.

Once you open the command line, you are often presented with a blank screen and a cursor at the bottom. Most command line programs start the lines from the bottom of the window and stack them upward with each newest command at the bottom of the stack.

Commands are location dependent and 

### Get started with git

#### Make sure you have git

To get started a great way to make sure we start well is to ensure we have `git` on this machine. Most machines should have it natively, but checking still helps, in our command line enter:

```sh
git --version
```

> This is a good pattern to remember. `tool-name --version` or `tool-name -v` will often tell you what version of the tool you are using (this is also handy to know), but if the machine knows the version, it implies it has it installed. Any flavor of `zsh: command not found: tool-name` means you need to install that tool. 

If for whatever reason you don't have `git` be sure to [download it](https://git-scm.com/downloads)

#### Check the status

Next let's see what is the status of our project, run:

```sh
git status
```

`git status` is one of the more often used commands just to see what files have been changed. It helps to know so you know what you are adding to your next commit.

#### Start a new git project

If we receive, `fatal: not a git repository (or any of the parent directories): .git`, that means this project has no git tracking yet. We can initiate `git` with:

```sh
git init
```

Then we can run git status again and see:

```sh
On branch main # What branch am I on?

No commits yet # What commit am I on?

Untracked files: # What changes are there?
  (use "git add <file>..." to include in what will be committed)
	filename.md
    file.sh
    script.js
    directory-name/
```

#### Staging changes

There are essentially three states for changes to be in:
- Untracked or modified: Changes since the last commit
- Staged: Changes that have been staged to be committed
- Committed: Changes that have been committed to a commit

Our status report above indicates that everything above is currently untracked. We can "stage" changes file-by-file with `git add`. Some examples of this look like:

```sh
# Adds one file
git add filename.md 

# Adds as many files as you name, separated by spaces
git add filename.md file.sh 

# Adds everything within the folder
git add directory-name

# Adds everything at your current working directory
# and all its children
# Note, this is not recommended since you may add
# more than you want to
git add .
```

If you do add more files than you want to you can use:

```sh
git restore --staged file.sh
```

#### Committing staged changes

Once you have all the files you want to include in this commit, you can use `git commit` to make that commit.

Your command line will open it's default editor then to have you write out the commit message. Often this is `vim` which can be tricky for beginners. You can exit `vim` by typing `:wq` which will "Write and quit" or save and quit. If you didn't type a commit message, the commit command will exit and you can try again with:

```sh
git commit -m "Write a good commit message"

# The `-m` flag is used with commit and expects a double-quote-wrapped string after it.
```

There are many opinions on writing good commit messages, but the basics are:

- The first word should be a present tense verb
- A single, clear sentence is best
- Be descriptive about what those changes do
- Be brief, but still be descriptive

Essentially when someone looks through the commits, they should read like a recipe, with clear instructions of how to recreate the work if they would like to learn how to make what you made!

#### Look through your commits

Once you've got some commits. You can look through them with `git log`. Looking at the logs is almost as common as looking at the status. At a glance you can see what changed, when it changed, who changed it, and, (if they wrote a good message) why they changed it.

The author, at the time of writing prefers the more condensed `git lg` which can be installed with [this guide](https://coderwall.com/p/euwpig/a-better-git-log). `git lg` has a little more color coding, a graph of how branches merge together, and is a little less noisy (for my taste anyway).

### When to commit

Commits are snapshots of your code at a certain time. These are often compared to save points in video games. When you make a mistake, you can load your last save point and try again with a new strategy.

**You should commit your changes when you know they work**

That way you can revert those changes and try a new way to tackle your issue.