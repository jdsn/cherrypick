# Example Repo for testing git cherry-pick

## Background
This repo reproduces an issue I discovered in a closed git
repo. Its just some pseudo code and a changes file.

## Reproduce
The steps to reproduce the issue are as simple as:
```
git clone https://github.com/jdsn/cherrypick.git
git checkout otherbranch
```

Now try to cherry-pick the last commit from master.
```
git cherry-pick master
```

This results in a conflict - which is understandable.
But the diff in the changes file is surprisingly long.
It is longer than expected as it contains more lines than
```
git show master
```

The cherry-pick picked all changes to the changes file from the
entire master branch instead of only the changed lines from the
last commit of master.
