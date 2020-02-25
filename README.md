# Git Branching & Team Workflow

For this lesson you will work alone, but imagine you are working
with a group of other developers. Imagine each commit along
the way as being added by a different member of your group.

The goal of the lesson is to show branching with Git and how you
can use branching to manage a workflow that involves multiple
developers.

## Overview

The material presented here is based on the article:
[A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/).

![Diagram 1: Complete workflow](images/1-complete-workflow.png)

This image shows the entires process outlined below. You could
follow these processes in a real project. In the course of a
project you might apply the steps outlined here several times.

## Getting Started

You'll start this exercise by forking and then cloning the [Git branching starter project](https://github.com/Product-College-Labs/Core-Git-Branching).

## Instructions

Imagine you are working on a screen play for a new movie. You
need to fix problems in the script, add new features, merge
solve conflicts and publish the work along the way.

Working on a team you will create branches to manage team workflow.

You need to have a currently published project always available
(Production).

Another branch will hold be where you develop the project (Develop).

Your team will have a member developing new features that may or may not be
incorporated in the future (New Feature).

At any point you will want to merge one or more of these branches.

### Rename character

The first step is to create a new branch you can use to develop new
features. It's important that the changes to this branch are
not visible until they are considered ready to be published.

Your goal: Create a new branch and rename the character. This
will be the Development branch.

- Create and checkout develop branch: `git checkout -b develop`
- Edit text to rename the young boy "George"
- `git add .`
- `git commit -m "Edited text to rename the young boy"`

![Diagram 2: Rename character](images/2-rename-character.png)

### Oh no! Fix typos

Sometimes your team will need to make changes to the existing
published version of a product. It's important to remove typos
from the currently published project. This is a Hot Fix

Check the current version of the project for typos.

- Checkout the master branch: `git checkout master`
- Edit text to fix typos
- Commit to master: `git add . && git commit -m "Fixed typos."`
- Push to production (GitHub repo): `git push origin master`
- View script on GitHub to verify typos are fixed, but young boy is not yet renamed

![Diagram 3: Typo fixes](images/3-typo-fixes.png)

These changes should be incorporated into the development branch.

- `git checkout develop`
- `git merge master`

![Diagram 4: Merge typo fixes](images/4-merge-typo-fixes.png)

### New Feature: Add new characters

Sometimes your team will need to create a new feature. On larger
teams it's safer to keep this out of the development branch until
the new feature is fully functioning.

The producers have suggested that adding a zookeeper to the story
would be a good idea. They may change their minds in the future.
Probably best to keep this in a new feature branch.

Add a New Feature branch where you can incorporate the zoo keeper.

- Be sure you're on the `develop` branch: `git status`
  - If not, run `git checkout develop`
- Create and checkout new branch: `git checkout -b zookeeper`
- Edit text to add the Zookeeper character to the plot
- Commit changes to `zookeeper` branch

![Diagram 5: New character](images/5-new-character.png)

### Improve story ending

The word from on top is that the ending is weak and needs work.
You'll need to fix it.

The ending is part of regular development your team is improving
something that is already there. This work should be done on the
development branch.

- Checkout develop branch: `git checkout develop`
- Edit text of last paragraph to improve the ending
- `git add .`
- `git commit -m "Improved the ending"`

![Diagram 6: New story ending](images/6-new-story-ending.png)

### Merge new character branch into develop

The new character ideas were approved! Be sure to proof read them
before merging them with main story under development.

- Be sure you're on the `develop` branch: `git checkout develop`
- Merge `zookeeper` branch into `develop`: `git merge zookeeper`
- Now, the ending doesn't include the new character! Add another sentence to include the Friendly Koala in the ending.

![Diagram 7: Merge new character](images/7-merge-new-character.png)

### Review new script and ship it!

When releasing a new version of a project you'll merge the develop
branch into the Production branch.

- Be sure you're on the `develop` branch: `git checkout develop`
- Code review (read the script once through to catch any errors)
- If all looks good, go to your master branch: `git checkout master`
- Merge all changes from development branch: `git merge develop`
- Now ship it! `git push origin master`

![Diagram 8: Complete workflow](images/1-complete-workflow.png)

### Additional Resources

- [Learn Git Branching](https://learngitbranching.js.org/)
