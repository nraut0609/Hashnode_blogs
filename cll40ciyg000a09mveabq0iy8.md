---
title: "Advance Git & GitHub Advance for DevOps Engineer"
datePublished: Wed Aug 09 2023 17:32:04 GMT+0000 (Coordinated Universal Time)
cuid: cll40ciyg000a09mveabq0iy8
slug: advance-git-github-advance-for-devops-engineer
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691600810345/c7a364f3-92f5-4dea-89a9-115c4c43a440.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691602213383/cc98bfd6-58de-4d40-aa8e-a16d1c5f099f.png
tags: github, git, devops, github-actions-1, gitcommands

---

## **What Is Git Rebase?**

Git rebase is a command that lets users integrate changes from one branch to another, and the logs are modified once the action is complete. Git rebase was developed to overcome merging’s shortcomings, specifically regarding logs.

```plaintext
git rebase <target-branch>
```

## **What Is Git Merge?**

Git merge is a command that allows developers to merge Git branches while the logs of commits on branches remain intact.

The merge wording can be confusing because we have two methods of merging branches and one of those ways is called “merge,” even though both procedures do essentially the same thing.

in summary, here’s an image that shows an initial branch, a Git rebase, and a Git merge.

```plaintext
git merge <source-branch>
```

## **The Workings of Git Rebase and Merge**

Git rebase takes all the changes, compresses them into a single patch and integrates this new patch onto the target branch. Then, it moves the completed work from one branch to another, typically the master branch. In the process, rebase flattens the history, removing unwanted entries.

Git merge, on the other hand, only changes the target branch and creates a commit, preserving the history of the source branch.

![10](https://git.logikum.hu/images/tutorials/merge-rebase/10.svg align="left")

## **Git Rebase and Git Merge Similarities**

Both the rebase and merge commands exist for the same reason: they combine the work of multiple developers into a single entity, integrating changes between branches. That about sums up their similarities. On the other hand, their differences are considerably more profound.

## **What’s the Difference Between Merge and Rebase?**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Merge</strong></p></td><td colspan="1" rowspan="1"><p><strong>Rebase</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>Git Merge lets you merge different Git branches.</p></td><td colspan="1" rowspan="1"><p>Git Rebase allows you to integrate the changes from one branch into another.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Git Merge logs show you the complete history of commit merging.</p></td><td colspan="1" rowspan="1"><p>Git Rebase logs are linear. As the commits are rebased, the history is altered to reflect this.</p></td></tr><tr><td colspan="1" rowspan="1"><p>All the commits on a feature branch are combined into a single commit on the master branch.</p></td><td colspan="1" rowspan="1"><p>All commits are rebased, and the same number of commits are added to the master branch.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Merge is best used when the target branch is supposed to be shared.</p></td><td colspan="1" rowspan="1"><p>Rebase is best used when the target branch is private.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Merge preserves history.</p></td><td colspan="1" rowspan="1"><p>Rebase rewrites history.</p></td></tr></tbody></table>

## **Let's Practice**

Open your terminal or command prompt and navigate to the desired directory where you want to create the repository.

* Initialize a new Git repository
    
    ```plaintext
      git init
    ```
    
* Create a new file called `version01.txt` with the specified content:
    
    ```plaintext
      mkdir Devops
      mkdir Git
      cat>version01.txt
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684615375017/ba22682b-9ea1-4831-8115-3fd5f6ecafad.png?auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684615441272/0b29e933-f848-419c-b9ed-8d8539bfa94d.png?auto=compress,format&format=webp align="left")

* Add the file to the staging area:
    

```plaintext
git add version01.txt
```

* Create and switch to the `dev` branch:
    
    ```plaintext
      git checkout -b dev
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684615549781/9c7f58c1-bcb9-47cc-b175-ab81bfe79974.png?auto=compress,format&format=webp align="left")

Commit the changes with the commit message "Added new feature":

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691596460768/f9e4e5ee-605d-411e-999d-b931979dc866.avif align="center")

```bash
git commit -m "Added new feature"
```

* Push the `dev` branch to the remote repository:
    
    before this, do remote login `git remote add origin <url>`
    
    ```plaintext
      git push -u origin dev
    ```
    

Add new commit in `dev` branch after adding Mentioned below content in Devops/Git/version01.txt: While writing the file make sure you write these lines

* <mark>1st line&gt;&gt; This is the bug fix in Development branch</mark>
    
* Commit this with Message “ Added feature2 in development branch”
    

```bash
cat>>version01.txt
This is the bug fix in development branch
git add version01.txt
git commit -m "Added feature2 in development branch"
git push -u origin dev
```

* <mark>2nd line&gt;&gt; This is gadbad code</mark>
    
* Commit this with message “ Added feature3 in development branch
    

```bash
echo "This is gadbad code" >> version01.txt
git add version01.txt
git commit -m "Added feature3 in development branch"
```

* <mark>3rd line&gt;&gt; This feature will gadbad everything from now.</mark>
    
* Commit with message “ Added feature4 in development branch"
    

```bash
echo "This feature will gadbad everything from now." >> version01.txt
git add version01.txt
git commit -m "Added feature4 in development branch"
git push -u origin dev
```

### Restore the file to a previous version where the content should be “This is the bug fix in the development branch”

restore the file to a previous version, you can use `git revert` command. Find the commit hash of the previous version (e.g., using `git log`, `git log --oneline`) and then run the following command:

```plaintext
git revert <commit_hash>
```

This will create a new commit that undoes the changes made in the specified commit.

Alternatively, if you want to completely reset the file to a previous version and discard the commits, you can use `git reset` command. Again, find the commit hash of the previous version and run the following command:

```bash
git reset <commit_hash> --hard
```

This will move the `dev` branch pointer to the specified commit, discarding any commits made after that point.

### **Add some changes to** `dev` branch and merge that branch in `master`

1. Ensure you are on the `dev` branch:
    

```plaintext
git checkout dev
```

1. Make the desired changes to your project files.
    
2. Stage the changes:
    

```plaintext
git add .
```

1. Commit the changes with an appropriate commit message:
    

```bash
git commit -m "Added changes to dev branch"
```

1. Switch back to the `master` branch:
    

```bash
git checkout master
```

1. Merge the `dev` branch into `master`:
    

```bash
git merge dev
```

1. Resolve any merge conflicts if they occur. Git will guide you through the process.
    
2. Commit the merge changes:
    

```bash
git commit -m "Merged dev branch into master"
```

1. Push the changes to the remote repository:
    

```bash
git push origin master
```

By following these steps, you will have added changes to the `dev` branch and merged it into the `master` branch, ensuring that the changes made in the `dev` branch are now incorporated into the `master` branch.

Please note that it's important to handle merge conflicts, if any, during the merge process. Adjust the branch names (`dev` and `master`) according to your specific branch names.

### As a practice try git rebase too, and see what difference you get.

```bash
git switch dev
vim version01.txt
git add .
git commit -m "trying git rebase"
git switch master
git rebase dev
```

### **.......................................................................**

### **Git Stash - Your Secret Weapon 🔧**

Need to switch branches but don't want to commit just yet? Use `git stash` to temporarily save changes. 📦 Stash list keeps track of your hidden gems.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691601734074/688ddc63-ccf7-483d-a28f-180ef5812d40.avif align="center")

### **Cherry-Pick - Tailored Commits 🍒**

Selectively apply specific commits from one branch to another with `git cherry-pick`. Perfect for bringing in those targeted improvements.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691601777019/95948949-fbd2-470d-8d46-1e71565e6b69.avif align="center")

### **Conflict Resolution - Taming the Merge Beast 🤝**

Resolve merge conflicts like a pro! `git status` for conflict files, `git diff` for clarity, and `git add` to signal victory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691601813447/62d8a57a-6695-4459-a4ff-61c1d46962d3.avif align="center")

**\*Task-01:**

* Create a new branch and make some changes to it.
    
* Use git stash to save the changes without committing them.
    
* Switch to a different branch, make some changes and commit them.
    
* Use git stash pop to bring the changes back and apply them on top of the new commits.
    

```bash
# Create a new branch and make some changes to it
git checkout -b new-branch

# Make some changes to the new branch
# (You can add, modify, or delete files here)

# Stash the changes without committing them
git stash save "My changes on new-branch"

# Switch to a different branch (e.g., main, master, or another branch)
git checkout different-branch

# Make some changes and commit them
# (You can add, modify, or delete files here)
git add .
git commit -m "Made changes on different-branch"

# Apply the stashed changes on top of the new commits
git stash pop
```

**\*Task-02:**

* In version01.txt of the development branch add the below lines after “This is the bug fix in development branch” that you added in Day10 and reverted to this commit.
    
* Line2&gt;&gt; After bug fixing, this is the new feature with minor alterations”
    
    Commit this with the message “ Added feature2.1 in development branch”
    
* Line3&gt;&gt; This is the advancement of the previous feature
    
    Commit this with the message “ Added feature2.2 in development branch”
    
* Line4&gt;&gt; Feature 2 is completed and ready for release
    
    Commit this with the message “ Feature2 completed”
    
* All these commits messages should be reflected in the Production branch too which will come out from the Master branch.
    
    ```bash
      # Edit version01.txt and add the specified lines
      # Then commit the changes separately
      echo "After bug fixing, this is the new feature with minor alteration" >> version01.txt
      git add version01.txt
      git commit -m "Added feature2.1 in development branch"
    
      echo "This is the advancement of previous feature" >> version01.txt
      git add version01.txt
      git commit -m "Added feature2.2 in development branch"
    
      echo "Feature 2 is completed and ready for release" >> version01.txt
      git add version01.txt
      git commit -m "Feature2 completed"
    ```
    

**\*Task-03:**

* In the Production branch Cherry pick Commit “Added feature2.2 in development branch” and added the below lines in it:
    
* The line to be added after Line3&gt;&gt; This is the advancement of the previous feature
    
* Line 4&gt;&gt;Added a few more changes to make it more optimized.
    
* Commit: Optimized the feature
    
    ```bash
      #Cherry pick the specified commit from the development branch
      git cherry-pick <commit-hash-of-Added-feature2.2>
    
      #Edit the file and add the specified lines
      #Then commit the changes
      echo "Added few more changes to make it more optimized." >> version01.txt
      git add version01.txt
      git commit -m "Optimized the feature"
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691602127321/10f23e96-ad22-4e0d-be2f-e92b5f2b84f8.jpeg align="center")