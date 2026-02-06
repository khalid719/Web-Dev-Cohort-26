---
title: "Git for Beginners: Basics and Essential Commands"
datePublished: Sat Jan 31 2026 09:18:37 GMT+0000 (Coordinated Universal Time)
cuid: cml23nqa9000502ibeenv4eu1
slug: git-for-beginners-basics-and-essential-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769850887515/3e424800-1130-4e74-a610-c92025c98519.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769851080652/0049adc2-4943-4255-bf7b-c5a9236eab67.png
tags: hiteshchoudharylco, hiteshchaudhary, chaicode, chaicohort, chaicode-webdev-cohort-2026, khaliddev

---

## 1\. What is Git

When a programmer starts coding, things look simple at first. You create a file, write some code, save it, and move on. But as time passes, the project grows. Files increase, logic becomes complex, and changes happen very frequently.

Now imagine you changed something today and tomorrow your code stops working. At that moment, you want to know exactly **what changed and when**. Without a system, this becomes almost impossible.

Git exists to solve this problem.

Git is a **version control system**. In simple terms, Git keeps a history of your project. It records how your code looked at different points in time and allows you to move back if needed.

Git is also **distributed**, which means every developer has the complete history of the project on their own machine. You are not dependent on the internet to see your past work.

So Git gives safety, confidence, and control to programmers.

## 2\. Why Git is used

Git is used because code is never static. It keeps changing.

Developers experiment, break things, fix bugs, add features, and refactor old code. Git allows all of this without fear because nothing is permanently lost.

If something goes wrong, Git allows you to go back to a previous commit. If you want to try a risky idea, Git allows you to do it safely. If multiple developers work together, Git allows everyone to contribute without conflicts.

That is why Git is not optional anymore. It is a core tool in software development.

## 3\. Git basics and core terminologies

Before using Git commands, some basic terms must be clear.

A **repository** is a project folder that Git tracks. Once Git is initialized, that folder becomes a repository.

A **commit** is a snapshot of your project. It represents a saved state of your code with a message explaining what changed.

A **branch** is a separate line of development. It allows you to work independently without touching the main code.

The **HEAD** is a pointer that shows where you currently are in the project history.

When Git is initialized, a hidden folder called `.git` is created. This folder stores all tracking data. Beginners should never manually modify this folder.

### a. Initializing a Git repository

To start using Git inside a project folder, we initialize it using:

```plaintext
git init
```

This command creates the `.git` folder and tells Git to start tracking changes in this directory.

From this moment, Git is active in the project.

### b. Checking project status

Before doing anything else, developers should frequently check the project state using:

```plaintext
git status
```

This command tells you:

* Which files are untracked
    
* Which files are modified
    
* Which files are staged for commit
    

Those colored dots and indicators you see in code editors come from Git status.

This command is one of the most important Git commands.

### c. Understanding git add properly

Git does not save changes automatically. Before committing, files must be staged using `git add`.

If you want to add **one specific file**, you do:

```plaintext
git add index.html
```

If you want to add **multiple specific files**, you do:

```plaintext
git add index.html style.css script.js
```

If you want to add **all changed files at once**, you do:

```plaintext
git add .
```

This stages everything that is modified or untracked.

The staging area exists so that developers can control **exactly what goes into a commit**. Nothing is committed unless it is added first.

### d. Creating a commit

Once files are staged, we create a commit using:

```plaintext
git commit -m "Added basic page layout"
```

A commit message should briefly explain what was changed.

Each commit creates a permanent record in Git history. This is why commits should represent meaningful checkpoints, not random saves.

### e. Viewing commit history

To see all commits made in the repository, we use:

```plaintext
git log
```

This shows:

* Commit IDs
    
* Author information
    
* Dates
    
* Commit messages
    

This history helps developers understand how a project evolved over time.

### f. Seeing exact changes using diff

Before committing, developers often want to see what exactly changed. For this, we use:

```plaintext
git diff
```

This command shows line-by-line changes made since the last commit.

It is very useful for reviewing code before saving it permanently.

### g. Working with branches

As projects grow, working directly on the main branch becomes risky.

Branches allow developers to work on features independently.

To create a branch:

```plaintext
git branch feature-auth
```

To switch to that branch:

```plaintext
git checkout feature-auth
```

Or using the newer command:

```plaintext
git switch feature-auth
```

To see all branches:

```plaintext
git branch
```

Branches give freedom to experiment without affecting stable code.

### h. Creating and connecting a GitHub repository

Git works locally, but GitHub is used to store code online.

After creating a repository on GitHub, we connect it to the local project using:

```plaintext
git remote add origin https://github.com/username/repository-name.git
```

To verify the connection:

```plaintext
git remote -v
```

This confirms that the local repository is linked to GitHub.

### i. Pushing and pulling code

To push local commits to GitHub for the first time:

```plaintext
git push -u origin main
```

After this setup, future pushes become simple:

```plaintext
git push
```

To bring changes from GitHub to your local machine:

```plaintext
git pull
```

These commands keep local and remote repositories in sync.

### j. Cleaning and correcting mistakes

Sometimes files are added by mistake.

To remove a tracked file:

```plaintext
git rm file.txt
```

To discard changes in a file:

```plaintext
git restore file.txt
```

To remove untracked files:

```plaintext
git clean -f
```

These commands help maintain a clean working directory.

## 4\. Basic developer workflow using Git

A typical workflow starts with `git init`. Code is written and modified.

After changes, `git status` is checked. `git diff` is used to review changes. Files are staged using `git add`, then saved using `git commit`.

When working with GitHub, commits are pushed using `git push`. Updates are pulled using `git pull`.

This cycle repeats continuously, while Git silently tracks everything.

## 5\. Final takeaway

Git is not just a tool for saving code. It is a system that gives structure, safety, and confidence to developers.

Once Git commands and workflow become familiar, development becomes more controlled and less stressful. This understanding is essential for anyone who wants to work on real-world projects.