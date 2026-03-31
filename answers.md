# Git Mini Exo — Answers

## Part 1: Setup & Config

Verify the git version:

    git --version

Configure your Git username and email:

    git config --global user.name "adembennjima"
    git config --global user.email "b00818393@essec.edu"

* * *

## Part 2: Create Your First Repository

Create a folder called `my-first-repo`:

    mkdir my-first-repo

Navigate into that folder:

    cd my-first-repo

Initialize a Git repository:

    git init

Create a file called `readme.txt`:

    touch readme.txt

* * *

## Part 3: Your First Commit

1. What command shows you the current state of your repository?  
`git status` — it shows untracked files, modified files, and staged changes.

2. What command stages `readme.txt` for commit?  
`git add readme.txt` — this puts the file into the staging area.

3. What command commits with the message "Add readme file"?  
`git commit -m "Add readme file"` — this saves the staged changes as a commit.

4. What command shows your commit history?  
`git log` — it displays the commit history with hashes, author, date, and messages.

* * *

## Part 4: Make Changes

1. Edit `readme.txt` and add a new line of text:

    echo "This is my first Git repository." > readme.txt
    echo "This line was added later for Part 4" >> readme.txt

2. What does `git status` show now?  
It shows `readme.txt` as modified under changes not staged for commit. That means Git detected changes, but they are not staged yet.

3. Stage and commit your changes with an appropriate message:

    git add readme.txt
    git commit -m "Update readme with new line"

4. How many commits do you have now?  
Two commits.

* * *

## Part 5: Exploration

`git diff` shows the differences between the current file contents and the last staged or committed version.

`git log --oneline` shows the commit history in a short one-line format.

* * *

## Part 6: Working with Branches

1. What command lists all branches in your repository?  
`git branch`

2. What command creates a new branch called `feature-script`?  
`git branch feature-script`

3. What command switches to the `feature-script` branch?  
`git checkout feature-script`

4. What single command creates and switches to a new branch called `dev`?  
`git checkout -b dev`

5. Switch back to the `feature-script` branch:  
`git checkout feature-script`

6. Verify you are on the correct branch:  
`git branch`

* * *

## Part 7: Create a Bash Script on a Branch

Script content (`install.sh`):

    #!/bin/bash
    echo "Starting installation..."
    sudo apt update
    sudo apt install -y curl
    echo "Installation complete!"

Make the script executable:

    chmod +x install.sh

Stage and commit:

    git add install.sh
    git commit -m "Add install script"

* * *

## Part 8: Merge Branches

1. Switch back to the `main` branch:  
`git checkout main`

2. Is `install.sh` present? Why or why not?  
No, not before merging, because it was created on the `feature-script` branch.

3. What command merges `feature-script` into `main`?  
`git merge feature-script`

4. What changed after the merge?  
`install.sh` appears on `main` after the merge.

5. What do you observe in the commit history?  
The history now contains commits from both branches.

6. What command deletes the `feature-script` branch after merging?  
`git branch -d feature-script`

* * *

## Part 9: Push to GitHub

What command links your local repo to GitHub?

    git remote add origin https://github.com/adembennjima/my-first-repo.git

What command pushes your commits to GitHub?

    git branch -M main
    git push -u origin main

* * *

## Part 10: Delete and Clone

Navigate out of the project folder:

    cd ..

Delete the local repository folder:

    rm -rf my-first-repo

Clone your repository from GitHub:

    git clone https://github.com/YOUR_USERNAME/my-first-repo.git

Verify your files are there:

    cd my-first-repo
    ls

* * *

## Reflection Questions

1. Why is version control useful?  
It helps track changes, restore older versions, and collaborate safely.

2. What is the difference between staging and committing?  
Staging prepares changes for the next commit; committing saves them permanently in Git history.

3. When should you make a commit?  
When you complete a small logical change, like a feature, fix, or update.

4. What is the difference between `git init` and `git clone`?  
`git init` creates a new repository. `git clone` copies an existing repository from a remote source.

5. Why should you write good commit messages?  
They make the project history easier to understand.

6. What is the purpose of using branches?  
Branches let you work on changes separately without affecting `main`.

7. When would you create a new branch instead of working on main?  
When building a feature, fixing a bug, or testing something new.