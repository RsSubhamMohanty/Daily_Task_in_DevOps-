## Task 1: Understanding Branches

Answer these in your day-23-notes.md:

What is a branch in Git?

          - A branch in Git is like a separate line of development.
          - By default, Git creates a branch called main.
          - When you create a new branch, you get a copy of your project at that moment.
          - You can make changes in that branch without affecting the main code.
          
Why do we use branches instead of committing everything to main?

          - If we work directly on main, any mistake can break the project.
          - Branches allow us to:
                     Test new features
                     Fix bugs safely
                     Experiment without risk
          - After testing, we can merge the branch into main.
          
What is HEAD in Git?

          - HEAD is a pointer (reference) in Git.
          - It always points to the current branch you are working on.
          - It also points to the latest commit of that branch.

     👉 Example:
          - If you are on main, then HEAD → main → latest commit
     👉 Simple Definition:
          - HEAD is a pointer to the current working branch and its latest commit.

What happens to your files when you switch branches?

         When you switch branches (git checkout branch-name):
         
             - Git changes your working directory to match that branch.
         Files will:
         
               Change if different in that branch
               Disappear if not present in that branch
               Appear if they exist in that branch

         👉 Important:

               Uncommitted changes may cause conflicts or be blocked.

          👉 Simple Answer:
          
               When you switch branches, Git updates your files to match that branch's version.

## Task 2: Branching Commands — Hands-On

     In your devops-git-practice repo, perform the following:
     
List all branches in your repo

               - git branch

Create a new branch called feature-1

              - git branch feature-1
              
Switch to feature-1

              - git checkout feature-1
              
Create a new branch and switch to it in a single command — call it feature-2

              - git checkout -b feature-2
              
Try using git switch to move between branches — how is it different from git checkout?

              - git switch feature-1
              - git switch main
              
Make a commit on feature-1 that does not exist on main

              - git switch feature-1
                echo "This is feature 1 work" > feature1.txt
                git add .
                git commit -m "Added feature1 file"
                
Switch back to main — verify that the commit from feature-1 is not there

              - git switch main
              👉 Now check files:
                      ls
                      
Delete a branch you no longer need

              - git branch -d feature-2
         👉 Force delete (if needed):
              - git branch -D feature-2 

              
## Task 3: Push to GitHub

Create a new repository on GitHub (do NOT initialize it with a README)

         👉 Go to: GitHub
                  Click New Repository
                  Enter name → devops-git-practice
                 ❗ IMPORTANT: Do NOT check "Add README"
                  Click Create Repository

Connect your local devops-git-practice repo to the GitHub remote

              - git remote add origin https://github.com/your-username/devops-git-practice.git
              - git remote -v
              
Push your main branch to GitHub

              - git push -u origin main
              
Push feature-1 branch to GitHub

              - git push -u origin feature-1
              
Verify both branches are visible on GitHub

              👉 Go to your repo on GitHub

                     Click branch dropdown
                     You should see:
                     main
                     feature-1
                     
Answer in your notes: What is the difference between origin and upstream?

              ✅ origin
                 origin is the default name of your remote repository
                 It points to your GitHub repo
                  Example:
                          git push origin main

              👉 Simple meaning:
                              origin = your remote repo (your GitHub project)   



               ✅ upstream
                   upstream means the default branch tracking relationship
                   It connects your local branch to a remote branch
                   Set using:     
                             git push -u origin main

               👉 After this:
                              main → tracks → origin/main
               👉 Now you can just use:        
                                        git push

## Task 4: Pull from GitHub

Make a change to a file directly on GitHub (use the GitHub editor)

                  ✅ Step 1: Make change directly on GitHub
                  👉 Open your repo on GitHub
                      Open any file (or create a new one like update.txt)
                      Click ✏️ Edit
                      Add some content:
                                        This change is made on GitHub
                      Click Commit changes
                      
Pull that change to your local repo

                  👉 Open terminal in your project folder
                      - git pull origin main
                  👉 What happens:
                                   Git checks remote (GitHub)
                                   Downloads new changes
                                   Merges them into your local branch
                  ✅ Step 3: Verify changes locally
                                   ls
                  👉 OR open the file:
                                       cat update.txt

                  👉 You will see the changes you made on GitHub ✅

                      
Answer in your notes: What is the difference between git fetch and git pull?

                 ✅ git fetch
                 👉 Step-by-step:
                                  Downloads changes from remote (GitHub)
                                  DOES NOT merge them
                                  Keeps changes separate for review
                 👉 Example:
                              git fetch origin
                 👉 Simple meaning:
                             Fetch = Download only (no changes in your working code) 


             ✅ git pull
            👉 Step-by-step:
                             Downloads changes from remote
                            Automatically merges into your current branch
            👉 Example:  
                        git pull origin main

            👉 Simple meaning:
                               Pull = Fetch + Merge      

## Task 5: Clone vs Fork

Clone any public repository from GitHub to your local machine

              ✅ Step 1: Clone a public repository
              👉 Go to GitHub
              👉 Open any public repo (example: freeCodeCamp repo)
                            Click Code
                            Copy URL (HTTPS)
                  - git clone https://github.com/owner/repository-name.git

              👉 Example:
                          - git clone https://github.com/freeCodeCamp/freeCodeCamp.git
                          
              👉 This will download the repo to your local machine
              
Fork the same repository on GitHub, then clone your fork

              - Open the same repo on GitHub
                Click Fork (top-right)
                It creates a copy in your account
             👉 Now your repo URL becomes:
                                           - https://github.com/your-username/repository-name.git
                 Clone your fork 
                                 - git clone https://github.com/your-username/repository-name.git
                                 
Answer in your notes:

What is the difference between clone and fork?

              ✅ Clone
                 Copy of a repository to your local machine
                 Used for working locally
                 Command:
                         git clone <repo-url>
              ✅ Fork
                 Copy of a repository to your GitHub account
                 Used when you don’t have permission to original repo
                 
When would you clone vs fork?

                   ✅ Use Clone when:
                       You own the repo
                       You have direct access
                       You just want to work locally

                   ✅ Use Fork when:
                       You want to contribute to someone else's project
                       You don’t have write access
                       You want your own copy on GitHub    

After forking, how do you keep your fork in sync with the original repo?

                   - git remote add upstream https://github.com/original-owner/repo.git
                   - git fetch upstream
                   - git merge upstream/main
                   - git push origin main


                               

              

