### GitHub Guide


### Contributing to the Devopscohort3 Repository

### 1. Fork, Clone, and Set Up Upstream

Fork the devospscohort repository

go to your own repository and clone the forked repo

```bash
git clone https://github.com/<YOUR-GITHUB-ACCOUNT>/devopscohort3.git
cd devopscohort3
git remote add upstream https://github.com/baraqheart/devopscohort3.git
```

You can verify the added remotes using:

```bash
git remote -v
```

The output should be like:

```bash
origin  https://github.com/<YOUR-GITHUB-ACCOUNT>/devopscohort3.git (fetch)
origin  https://github.com/<YOUR-GITHUB-ACCOUNT>/devopscohort3.git (push)
upstream        https://github.com/wiepteam/devopscohort3.git (fetch)
upstream        https://github.com/wiepteam/devopscohort3.git (push)
```

### 2. Create a New Branch

For each new week of assignments, create a new branch named `cohort-3-lab-#` (replace # with the current assignment number):

```bash
git checkout -b cohort-3-lab-#
```

### 3. Make Your Changes, Commit and Push

**Assigments**
- this directory consists of labs and demo assignments regularly
  updated to improve your skills.
- to contribute to this repo, practice the labs and document them
  in a mark down file

**Submissions**

- create a directory with your name
- using the name the fact exact name from the asssinment directory
- create a mark down file for the lab you want to attempt

&#x2757;**Important:** Stage your changes, commit with a clear message following the assigment number, and push your branch:

```bash
git add .
git commit -m "Added lab #"
git push -u origin cohort-3-lab-#
```

### 4. Open a Pull Request

Go to your forked devopscohort3 repository on GitHub. Open a Pull Request by clicking `Compare & pull request`.

#### Select repositories:

- **Base Repository**: baraqheart/devopscohort3  
- **Base Branch**: main  
- **Head Repository**: your-github-account/devopscohort3 
- **Head Branch**: cohort-3-lab-# 

For the title, use this template: `YOUR-NAME: Cohort 3 lab #`.

Then, on the next screen, click `Create pull request` to finalize it.

Actively monitor your open PR. You will normally receive email notifications for any updates, comments, or requested changes. 
If reviewer feedback is provided, simply make your changes, add new commits, and push them again like in [Step 3](#3-make-your-changes-commit-and-push) until your PR is merged.

&#x1F4CC; When your PR is open and you need to make changes in the code, simply edit your files, commit, and push again. Your updates will automatically be added to the same PR until it is closed or merged.

Congratulations! You've successfully made your first open-source contribution to the **devopscohort3** repository! &#x1F389;

### 5. Weekly Updates: Syncing with Upstream and Making New Contributions

At the start of each new week (after your previous PR merges), update your local main to get all the latest changes:

```bash
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
```

&#x1F4CC; You may have to resolve conflicts after the merge. Conflict resolution depends on your IDE. To master merge, watch [this video](https://www.youtube.com/watch?v=Sqsz1-o7nXk&t=373s). You can also look for guides specific to your IDE or reach out to us on [Discord](https://discord.gg/JvEVfKBY6W) for support.

Now, repeat steps [2](#2-create-a-new-branch) to [4](#4-open-a-pull-request), from creating a new branch to opening a pull request, for your weekly contribution.



## Resources

- [Github blog](https://github.blog/developer-skills/github/)

- [Github: Pull requests documentation](https://docs.github.com/en/pull-requests)