---
title: "Inside Git: How It Works and the Role of the .git Folder"
datePublished: Sat Jan 31 2026 11:47:45 GMT+0000 (Coordinated Universal Time)
cuid: cml28ziwr000302jvethc9pel
slug: inside-git-how-it-works-and-the-role-of-the-git-folder
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769860011200/719fe150-117e-4781-b6fc-fc88cc649a72.png
tags: hiteshchoudharylco, hiteshchaudhary, chaicode, chaicode-webdev-cohort-2026, khaliddev

---

## 1\. How Git works internally

When I started using Git, it always felt like some kind of magic. I used to type `git add` and `git commit`, and Git would somehow remember everything. For a long time, I was using Git without really knowing what it was doing behind the scenes.

Later, when I tried to understand Git internally, one thing became very clear to me. Git is not doing anything magical. It is just very well designed.

The biggest realization for me was this: Git does not track changes, it tracks **snapshots**. Instead of thinking about what changed, Git thinks about what the project looks like at a particular moment.

Once this clicked, Git started making much more sense.

## 2\. Understanding the `.git` folder

The first thing I noticed was the `.git` folder.

When I ran:

```plaintext
git init
```

a hidden folder named `.git` appeared inside the project. At first, I ignored it. But later I realized that this folder is actually the core of Git.

Everything Git knows about the project lives inside this `.git` folder. My code files are outside, but Git’s entire memory is inside this folder.

If this folder is deleted, Git completely forgets the project history. That alone tells how important it is.

I also understood why we are told not to touch this folder manually. One small change inside it can break the whole history.

## 3\. Git objects: Blob, Tree, Commit

While digging deeper, I learned that Git stores data in the form of objects. Understanding these objects helped me build a clear picture.

A **blob** stores the actual content of a file. It does not store the file name. That surprised me at first. If two files have the same content, Git stores only one blob and reuses it.

Then comes the **tree** object. A tree represents a directory. It connects file names to blobs and folders to other trees. This is how Git understands the structure of the project.

Finally, there is the **commit** object. A commit points to a tree and also stores metadata like author, time, and commit message. It also points to the previous commit.

So internally, Git is just connecting blobs, trees, and commits in a very structured way.

## 4\. What actually happens during `git add`

Earlier, I used to think `git add` saves the file. That is not true.

When I modified a file and ran:

```plaintext
git add index.html
```

Git did something very specific. It read the file content, created a blob object from it, and stored that blob inside the `.git` folder. At the same time, it updated the staging area to point to this blob.

This made me understand why the staging area exists. It is not a temporary file. It is Git’s way of preparing a snapshot.

Until a file is added, Git simply ignores it during commit.

## 5\. What actually happens during `git commit`

When I run:

```plaintext
git commit -m "Added homepage layout"
```

Git does not scan all files again. It already knows what is staged.

Git takes the staged blobs, creates a tree that represents the folder structure, and then creates a commit object that points to that tree and the previous commit.

After that, the current branch pointer moves to this new commit.

This explains why commits are fast and why only staged files are included.

## 6\. How Git tracks changes over time

Another thing that became clear to me is how Git tracks changes.

Git does not store differences between files in the way I initially imagined. Each commit points to a full snapshot of the project.

If a file has not changed, Git simply reuses the existing blob. That is why Git does not waste space and why switching branches feels instant.

This snapshot-based model is the reason Git handles branching so efficiently.

## 7\. How Git uses hashes for integrity

One of the most impressive parts of Git is how it uses hashes.

Every object in Git is identified by a hash generated from its content. If the content changes even slightly, the hash changes completely.

This means Git can immediately detect corruption or tampering. Since commits also include hashes of their parent commits, the entire history becomes a chain.

Once I understood this, I realized why Git history is so reliable.

## 8\. The mental model that helped me

Instead of remembering commands, this mental model helped me more:

My files live outside Git.  
Git stores snapshots inside the `.git` folder.  
`git add` prepares content.  
`git commit` records a snapshot.  
Branches are just pointers.  
HEAD tells Git where I am.

Once I started thinking this way, Git commands stopped feeling scary.