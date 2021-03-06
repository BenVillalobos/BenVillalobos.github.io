---
title: "Clean & Speed Up Your Local Git Repo With Three Commands"
categories:
tags:
  - dev
  - tips
---

Sometimes ya gotta force push or rebase and leave some commits behind. On a large repo with many commits and remotes, your git commands could actually slow down with too many objects floating around. Consider running these commands to help keep things in tip top shape.

### [git gc](https://git-scm.com/docs/git-gc)

Compresses and removes orphaned objects, thus speeding up commands in your local repo. Nice!
![image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cb5hr4zezeppwg87c6s8.png)

### [git fsck](https://git-scm.com/docs/git-fsck)

Yes, I misread that too. `git fsck` shows you all orphan or dangling objects in your local repo. I cleaned up recently so mine isn't too bad.
![image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3i5l2hitr5xw5u6sn0dv.png)

### [git prune](https://git-scm.com/docs/git-prune)

If you don't plan on doing anything with the objects you saw using fsck, run `git prune` to clear them out. If you'd like to see what would be cleaned out without actually deleting them, run `git prune -n` for a dry-run.
![image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/evk0n3wrxhjgtajsbmtk.png)
 
In theory, cleanup happens somewhat regularly when running some of git's main commands. I haven't noticed, or is it just good at its job. In any case, I hope this helped!

I learned about these commands from the amazing [Git Internals pdf](https://github.com/pluralsight/git-internals-pdf). Every dev should read it.
