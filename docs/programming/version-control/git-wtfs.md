# Git Weird Technical Failures (WTFs)

## HEAD detached at ...?

```bash
$ git status
HEAD detached at 1193e06
Untracked files:
  (use "git add <file>..." to include in what will be commited)

        ../seitan/

nothing added to commit but untracked files preset (use "git add" to track)
```

### No Modifications
Chances are, you’ve probably used the git checkout command without specifying a file (or a directory). That’s OK! If you haven’t made any changes, you can fix this by using the command git checkout master. If everything is ok, you should a message similar to this:

```bash
``$ git checkout master
Previous HEAD position was b405852... added tofu recipes
Switched to branch 'master'
You have resolved the issue!
```

### With Modifications
If you have made some changes (i.e. using the command git status tells you that you have modified some file(s) like the image below), there are a few more steps to take.

```bash
$ git status
HEAD detached at 1193e06
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

        modified: kung_pao_tofu.txt

Untracked files:
(use "git add <file>..." to include in what will be commited)

        ../seitan/

no changes added to commit (use "git add" and/or "git commit -a")
```
First, use the command `git stash`. Your modifications may have magically disappeared! Don’t worry-we'll be able to retrieve them in a second!

```bash
$ git stash
Saved working directory and index state WIP on (no branch): 1193e06 added tofu
recipes HEAD is now at 1193e06 added tofu recipes

$ git status
HEAD detached at 1193e06
Untracked files:
(use "git add <file>..." to include in what will be commited)

        ../seitan/

nothing added to commit but untracked files preset (use "git add" to track)
```
From here, use the command `git checkout master`. You should see the all clear message from before:

```bash
$ git checkout master
Previous HEAD position was b405852... added tofu recipes
Switched to branch 'master'
```
Almost done! Let’s go get our changes. Use git stash pop. But wait, we’ve got a conflict!

```bash
$ git stash pop
Auto-merging tofu/kung_pao_tofu.txt
CONFLICT (content): Merge conflict in tofu/kung_pao_tofu.txt
```
```bash
$ git status
On branch master
Unmerged paths:
(use "git reset HEAD <file>..." to unstage)
(use "git add <file>..." to mark resolution)

        both modified: kung_pao_tofu.txt

Untracked files:
(use "git add <file>..." to include in what will be committed)

        ../seitan/

no changes added to commit (use "git add" and/or "git commit -a")
```

Now use git stash drop:
```bash
$ git stash drop
Dropped refs/stash@{0} (57f0ac5c5480964cdf29a94ed6b87e38da823488)<Paste>
```
Now we’ve got to fix these merge conflicts!

## Error: failed to push some refs?
Sometimes when working with others, you’ll get a message like this when you push:

```bash
$ git push origin master
To https://github.com/gilbertghang/recipes.git
! [rejected]     master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/gilbertghang/recipes.git"
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
What has happened here is that your remote (i.e. your online Github repository) contains commits that your local repository does not have. Luckily, Git is very good about telling you how to fix these errors: if you read the error message carefully, you’ll see that is suggests that you git pull. Do that, fix any merge conflicts, and push. Done!

## What are all these `>>>>>>` symbols in my code?
Sometimes when you pull from a repository, you’ll get a message like this when you pull:

```bash
$ git pull origin master
From github.com:Berkeley-CS61B/course-materials-su20
* branch            master     -> FETCH_HEAD
  Auto-merging proj/proj0/solution/canonical/Body.java
  CONFLICT (content): Merge conflict in proj/proj0/solution/canonical/Body.java
  Automatic merge failed; fix conflicts and then commit the result.
```
  The problem here is that the code on your computer had a conflict with the code in the remote repository you’re pulling from, and Git couldn’t figure out how to resolve it. Since it is unsure, Git refuses to overwrite your local code.

However, when you open your Body.java, you see some kind of crazy garbage like:

```java
public Body(Body p) {
<<<<<<< HEAD
    this.xPos = p.xPos;
    this.yPos = p.yPos;
=======
    this.xxPos = p.xxPos;
    this.yyPos = p.yyPos;
>>>>>>> 27ddd0c71515e5cfc7f58a43bcf0e2144c127aed
```
This is a good thing! Everything between `<<<<<<< HEAD` and `=======` is what was on your computer, and everything between `=======` and `27ddd0c71515e5cfc7f58a43bcf0e2144c127aed` is what was on the remote server.

Your job is to look for these and resolve the merge conflict yourself. In this case, the remote repository is right, so we simply delete out everything between `<<<<<<< HEAD` and `=======`, and also delete the `>>>>>>> 27ddd0c71515e5cfc7f58a43bcf0e2144c127aed` marker, leaving:

```java
public Body(Body p) {
    this.xxPos = p.xxPos;
    this.yyPos = p.yyPos;
```
Once you’ve resolved all of your merge conflicts, add all the files you manually edited, and commit them as usual, e.g.

```java
git add Body.java
git commit -m "resolved merge conflict"
git push origin master
Cannot pull due to uncommitted changes
Sometimes your repo will not let you update its code versions if you have local changes that would be overwritten by the merge. You’ll get an error like this:

$ git pull origin master
From github.com:Berkeley-CS61B/course-materials-su20
* branch            master     -> FETCH_HEAD
  error: Your local changes to the following files would be overwritten by merge:
  fileOne.java
  fileTwo.java
  Please commit your changes or stash them before you merge.
  Aborting
  Updating 554234...a8dh34
```

If we `git add fileOne.java` and `git add fileTwo.java` and then commit our files, we can then proceed with the pull as expected.

Alternatively, you can use stash:

`git stash push` temporarily stashes all your local changes and reverts back to the HEAD commit.

`git stash pop` removes the most recent stash and applies it to the top of the current working tree. I.E. this is the reverse process of git stash push.

Credit from UC Berkeley's COMPSCI61BL SU2023 Git WTFs. View the original [here](https://cs61bl.org/su23/guides/git-wtfs).