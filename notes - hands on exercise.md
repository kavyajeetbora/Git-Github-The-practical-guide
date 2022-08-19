# Example

## Adding a file/files for tracking

This way the git will know which file to track and which not to. This is done by pushing the selected files to the staging area

Here in this example we add two text files for simplicity:

```git
echo hello > file1.txt
echo hello > file2.txt
```
Here the message 'hello' is stored in the file using `>` character

Now with `git status` we can check which files are tracked and which are not:

```git
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    hello.py
        deleted:    playground.ipynb
        deleted:    readme.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file1.txt
        file2.txt
        git_project.md

no changes added to commit (use "git add" and/or "git commit -a")
```

To add the files to the staging area, we need to add the files using:

for single file:
```git
git add file1.txt
```
for mulitple files, we can add the files in series separated by space or we can use patterns:
```git
git add file1.txt file2.txt
```
or
```git
git add *.txt
```

Now after adding we can check the status:
```git
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file1.txt
        new file:   file2.txt
        new file:   git_project.md
        deleted:    hello.py
        deleted:    playground.ipynb
        deleted:    readme.md
```

## Modifying the files
```git
git world >> file1.txt
```
Note: here the `>>` character means append the text to the file.
The git statis shows:
```git
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file1.txt
        new file:   file2.txt
        new file:   git_project.md
        deleted:    hello.py
        deleted:    playground.ipynb
        deleted:    readme.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file1.txt
        modified:   git_project.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        example.md
```

**Note:** Now here there is an important thing to note is that the changes are not staged in the staging area yet. As you can see in the output above. it says the changes are not yet staged.

Hence to stage the changes we need to use `git add` everytime:

```git 
git add file1.txt
```

## Commiting changes

This is where make the changes permanent. To Commit the changes we type:
```
git commit -m "initial commit"
```

We commit using a `-m` message attribute and with a message. To main purpose of the message is for our reference. This is when we want to retrieve files of previous versions.

Also sometimes we want to have a detailed message as sometimes the message is not enough to explain the changes. Hence we just type

```git 
git commit 
```

and then it will open a file in the vs code, where we can type the message. Once the file is closed the commit is performed.

After this everything in the staging area is cleaned and there is no more changes to be updated.

Output:

```
$ git commit -m "initial commit"
[master f901f5c] initial commit
 7 files changed, 167 insertions(+), 11 deletions(-)
 create mode 100644 example.md
 create mode 100644 file1.txt
 create mode 100644 file2.txt
 create mode 100644 git_project.md
 delete mode 100644 hello.py
 delete mode 100644 playground.ipynb
 delete mode 100644 readme.md
```
Here the git will specify the changes in terms of number of lines inserted and deleted. Also specify which files were added and deleted
