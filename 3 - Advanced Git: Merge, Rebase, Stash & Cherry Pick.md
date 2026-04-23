## Task 1: Git Merge

## Create a new branch feature-login from main, add a couple of commits to it

We’ll do everything in terminal :-

        - mkdir git-merge-practice
        - cd git-merge-practice
        - git init
        
## Switch back to main and merge feature-login into main
Create first file:-

        - echo "My App" > app.txt
        - git add .
        - git commit -m "Initial commit"

Rename branch to main:-

        - git branch -M main

## Switch back to main and merge feature-login into main

Step 1: Create Branch feature-login

        - git checkout -b feature-login

Step 2: Add Couple of Commits

       - echo "Login page created" >> app.txt
       - git add .
       - git commit -m "Added login page"

Second commit:

       - echo "Login validation added" >> app.txt
       - git add .
       - git commit -m "Added login validation"

## Observe the merge — did Git do a fast-forward merge or a merge commit?

 Go Back to Main

       - git checkout main

 Merge feature-login

       - git merge feature-login

## Now create another branch feature-signup, add commits to it — but also add a commit to main before merging

  Create feature-signup Branch
  
          - git checkout -b feature-signup

  Add commit:    

          - echo "Signup page created" >> app.txt
          - git add .
          - git commit -m "Added signup page"

## Merge feature-signup into main — what happens this time?
          
  Go Back to Main

          - git checkout main

  Now add something directly to main:

          - echo "Homepage updated" >> app.txt
          - git add .
          - git commit -m "Updated homepage"

Merge feature-signup into main

          - git merge feature-signup

Answer in your notes:
## What is a fast-forward merge?

    - Fast-forward merge: Happens when the target branch has no new commits since the feature branch was created. Git simply moves the branch pointer forward to the latest commit without creating a new merge commit.

## When does Git create a merge commit instead?

    - When Git creates a merge commit: Git creates a merge commit when both branches have new commits, so their histories have diverged and need to be combined.

## What is a merge conflict? (try creating one intentionally by editing the same line in both branches)

     - Merge conflict: A merge conflict happens when Git cannot automatically combine changes, usually because the same line in a file was edited differently in both branches. It must be resolved manually.


## Task 2: Git Rebase

## Create a branch feature-dashboard from main, add 2-3 commits

        - git checkout main
        - git checkout -b feature-dashboard
Add 2–3 commits in feature-dashboard

        - echo "Dashboard page" >> app.txt
        - git add .
        - git commit -m "Added dashboard page"

        - echo "Dashboard stats" >> app.txt
        - git add .
        - git commit -m "Added dashboard stats"

        - echo "Dashboard styling" >> app.txt
        - git add .
        - git commit -m "Added dashboard styling"

## While on main, add a new commit (so main moves ahead)

       - git checkout main

       - echo "Homepage update" >> app.txt
       - git add .
       - git commit -m "Updated homepage" 

 ## Switch to feature-dashboard and rebase it onto main

       - git checkout feature-dashboard

Rebase onto main 

       - git rebase main

## Observe your git log --oneline --graph --all — how does the history look compared to a merge?

        - git log --oneline --graph --all 

## Answer in your notes:
## What does rebase actually do to your commits?      

     - Rebase takes your branch commits, moves them to the latest base branch, and reapplies them on top of it as new commits.

## How is the history different from a merge?

     - Rebase creates a clean, straight history without merge commits. Merge keeps branch history and adds a merge commit.

## Why should you never rebase commits that have been pushed and shared with others?

    - Rebase rewrites commit history by creating new commit IDs, which can cause confusion and conflicts for others who already pulled the old commits.

## When would you use rebase vs merge?

    - Use rebase for cleaning up local branch history before merging. Use merge when combining shared branches and preserving complete history.    


## Squash Commit vs Merge Commit

Create a branch feature-profile, add 4-5 small commits (typo fix, formatting, etc.)

     - git checkout main
     - git checkout -b feature-profile
     - echo "Profile page created" >> app.txt
     - git add .
     - git commit -m "Created profile page"
     - echo "Fixed typo in profile" >> app.txt
     - git add .
     - git commit -m "Fixed typo"
     - echo "Formatted profile page" >> app.txt
     - git add .
     - git commit -m "Formatting update"
     - echo "Added profile image" >> app.txt
     - git add .
     - git commit -m "Added profile image"

## Merge it into main using --squash — what happens?

     - git checkout main
     - git merge --squash feature-profile
     - git commit -m "Added profile feature"

## Check git log — how many commits were added to main?

     - git log --oneline --graph

## Now create another branch feature-settings, add a few commits

     - git checkout -b feature-settings
     - echo "Settings page created" >> app.txt
     - git add .
     - git commit -m "Created settings page"

     - echo "Dark mode added" >> app.txt
     - git add .
     - git commit -m "Added dark mode"

     - echo "Notification settings added" >> app.txt
     - git add .
     - git commit -m "Added notifications"

## Merge it into main without --squash (regular merge) — compare the history

      - git checkout main
      - git merge feature-settings
      - git log --oneline --graph

## What does squash merging do?

      - Squash merge combines all branch commits into one single commit before merging into main.

## When would you use squash merge vs regular merge?

      - Use squash merge when branch has many small messy commits and you want clean history.
      - Use regular merge when you want to keep all commit history.  

## What is the trade-off of squashing?

      - You lose individual commit history of that branch because all commits become one commit.
      
     
        
       
        
     
     
          
          
       






