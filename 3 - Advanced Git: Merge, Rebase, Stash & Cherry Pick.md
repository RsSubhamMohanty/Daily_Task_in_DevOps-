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
     
          
          
       






