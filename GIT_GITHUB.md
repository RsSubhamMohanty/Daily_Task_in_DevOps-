## Task 1: Install and Configure Git

Verify Git is installed on your machine

          - git --version

Set up your Git identity — name and email

          - git config --global user.name "Your Name"
          - git config --global user.email "youremail@example.com"

Verify your configuration

          - git config --list

Check the output for the user.name and user.email lines. Alternatively, you can check them individually:

          - git config user.name
          - git config user.email
          
## Task 2: Create Your Git Project

Create a new folder called devops-git-practice

          - mkdir devops-git-practice
          - cd devops-git-practice

Initialize the Git Repository

          - git init

Check the Status

          - git status

Explore the Hidden .git/ Directory

          - ls -Force
          - cd .git; ls

After exploring the .git folder, remember to move back up to your main project folder so you can start coding:

          - cd ..

## Task 3: Create Your Git Commands Reference

Create a file called git-commands.md inside the repo

           - vim git-commands.md

Add the Git commands you've used so far, organized by category:

Setup & Config
Basic Workflow
Viewing Changes  

For each command, write:
What it does (1 line)
An example of how to use it

             - git status

## Task 4: Stage and Commit

Stage your file

             - git add git-commands.md

Check what's staged

             - git status

Commit with a meaningful message

             - git commit -m " This is my First commit "

View your commit history

            - git log

## Task 5: Make More Changes and Build History

Edit git-commands.md — add more commands as you discover them

             - git-commands.md
             - git log --oneline

Check What Changed

              - git diff

The "Stage and Commit" Cycle (Repeat 3 Times)

Iteration 1: Add a "Branching" section

              - git add git-commands.md
              -  git commit -m "docs: add section for branching commands"

Iteration 2: Fix a typo or add a formatting change

              - git add git-commands.md
              - git commit -m "style: improve markdown formatting for readability"

Iteration 3: Add a "Remote" section (for GitHub)

              - git add git-commands.md
              - git commit -m "docs: add git remote and git push definitions"

View Your History in Compact Format

              - git log --oneline --graph --all


## Task 6: Understand the Git Workflow

1.What is the difference between git add and git commit?

  git add vs. git commit
  git add: This is like picking up an item and putting it into a shipping box. You are selecting which specific changes you want to include in your next "save."

  git commit: This is like sealing the box and putting a label on it. It permanently records the "snapshot" into your project's history.

2.What does the staging area do? Why doesn't Git just commit directly?

 Why not just commit directly?
The staging area gives you control. Imagine you fixed a bug in one file but also started a new feature in another file. You might want to commit the bug fix now but keep the unfinished feature out of the history. Staging lets you hand-pick exactly what goes into each "save" so your history stays clean and organized.

3. What git log Shows
It is the flight recorder for your project. It shows:

The unique ID (Hash) of every commit.

Who made the change (Author).

When it happened (Date/Time).

What was done (Commit Message).

4. The .git/ Folder
This hidden folder is the brain of your repository. It contains the entire history of your project.

What happens if you delete it? Your current files (the "Working Directory") stay exactly as they are, but your entire version history vanishes. It becomes a regular folder again, and you can no longer "go back in time" to previous versions.


5. Working Directory vs. Staging Area vs. Repository
Working Directory: Your actual folder on your computer where you are currently typing and editing files (the "Present").

Staging Area: A middle ground where you prepare changes for the next commit (the "Draft").

Repository: The database where Git stores all your past commits and branches (the "Permanent Record").

When you finish writing these, don't forget to stage and commit your new day-22-notes.md file!

                     - git add day-22-notes.md
                     - git commit -m "docs: add conceptual notes on git workflow"
              


              
             

             

          

          
