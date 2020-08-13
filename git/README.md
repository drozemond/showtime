# SHOWTIME

# Squash commits

Generate the scenarion of multiple commits
```
git init demo && cd demo

echo "First commit" > README.md \
&& git add -A  \
&& git commit -m "First commit"

echo "Second commit" > README.md \
&& git add -A  \
&& git commit -m "Second commit"

echo "Third commit" > README.md \
&& git add -A  \
&& git commit -m "Third commit"

echo "Fourth commit" > README.md \
&& git add -A  \
&& git commit -m "Fourth commit"

echo "Fifth commit" > README.md \
&& git add -A  \
&& git commit -m "Fifth commit"
```
Check the log
```
git log --pretty=oneline
```
Rebase your commits, and squash some
```
git rebase -i <id>~1
```
Check log again for result
```
git log --pretty=oneline
```

# Rebase onto master

First we generate a scneario where a merge conflict would occur.

A common commit on master
```
echo "common commit" > README.md \
&& git add -A  \
&& git commit -m "Common commit"
```

Simulate developer #1 creating his/her feature branch and doing some work
```
git checkout -b branch1 \
&& echo “branch1” > README.md \
&& git add -A  \
&& git commit -m "Branch #1 commit"
```
Go back to master
```
git checkout master
```
Simulate developer #2 creating his/her feature branch and doing some work (on the same file)
```
git checkout -b branch2 \
&& echo “branch2” > README.md \
&& git add -A  \
&& git commit -m "Branch #2 commit"
```

Simulate develper #1 merging before developer #2
```
git checkout master
git merge branch1
```

Simulate being developer #2 needing to updating his/her branch before merging
```
git checkout branch2
```
Then we rebase from our feature branch onto master
```
git rebase master
```
which show us the conflicted files. Edit your files and resolve your merge conflicts, then add/stage your files to the commit
```
git add README.md
```
and continue rebase
```
git rebase --continue
```
Keep resolving merge conflicts untill there are no more.
Take your time and don't panic.
