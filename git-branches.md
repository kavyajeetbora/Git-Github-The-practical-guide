# Git Merge

## Understanding merge types

There are mainly two types of merge in git:
- Fast forward merge
- non fast forward
    - recursive 
    - Octopus
    - ours
    - Subtree

Out of the above, most common type of merges are fast forward and recursive non fast forward

>>### Fast forward merge
the fast forward merge is the most common one. git uses fast forward when there is additional commit in the master branch after the feature branch was created. 

The head is moved from the feature to the master branch. It is continuous single flow of commits.

```git
>git log
commit 45029b8678406ce1e3194a25b1893a8a5b70924d (HEAD -> master, feature)
    f2
commit 6ab73a983ab7a0b5592280b5b620db0775425098
    f1
commit 4bd5bd6d382f8242a7c053799ff5a58ab7100e07
    m2
commit 60a2ddcb54140cfb801abe3d865e20550b28d53a
    m1
```

- So here when the merge is done and given that there is no further commits in the master branch after feature branch was created, 
- then the merge is fast forward type meaning when the merge is done the head from the master to the latest commit in the feature branch (f2)
- Important thing to note here is that when feature branch are commited, then the feature branch also contains the additional two commits of the master branch
- **with fast forward merege, we dont create a new commit, we just move the pointer/header from the master to the lastest commit of the feature branch** 

In the master branch, if we go and rest to 2 commits before then the head/pointer moves to m2 commit of the master
