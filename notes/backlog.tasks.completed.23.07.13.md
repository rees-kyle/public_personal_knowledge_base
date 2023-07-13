---
id: fd2rs5gcz3y9vwubnbicuu6
title: '13'
desc: ''
updated: 1689211290988
created: 1689211111889
---

1. [x] place both repos in one drive 
1. [x] untrack scratch.md for both private and public repos
    1. [x] private
        1. [x] add scratch.md to .gitignore
        1. [x] remove scratch.md from index
    1. [x] public
        1. [x] add scratch.md to .gitignore
        1. [x] remove scratch.md from index
1. [x] add standards.backlog.md
1. [x] modify backlog.md
## hierarchy
```mermaid
graph TD;
    topic-->guide;
```
1. [x] rename syntax.md to guide.md
1. [x] modify guide.md
    1. [x] when renaming a note that has a parent use Dendron: Refactor Hierarchy command
    1. [x] flow chart
## hierarchy
```mermaid
graph TD;
    version-control-system-->git;
    software-->apps-->git-bash-->guide;
```
1. [x] add version-control-system.md
1. [x] modify version-control-system.md
1. [x] add version-control-system.git.md
1. [x] modify version-control-system.git.md
1. [x] add git-bash.md
1. [x] modify git-bash.md
1. [x] add git-bash.guide.md
1. [x] modify git-bash.guide.md (To stop tracking a file, we must remove it from the index:
git rm --cached file.ext)