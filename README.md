![Git & Githib](img/git&githubimage.png)

# Git and Github Notes: 
Understanding Git, version control, and Github broken down. 

## Table of Contents
- [What is Git ?](#what-is-git)
- [What is Git used for ?](#what-is-git-used-for)
- [What does Git do ?](#what-does-git-do)
- [How Git works](#what-does-git-do)
- [Getting Started with Git (for mac users)](#getting-started-with-git-for-mac-users)
- [Github Basics](#github)
- [Creating a Project](#developing-a-project)
    

## What is Git ?
- Git is a free and open source version control system. Git is a very popular version control system tool used today. 

## What is Git used for ?
- Git allows developers to track changes in the code. Some changes include:
    - Who made the change ?
    - What changes were made ?
    - When the changes were made ?
- It is also used for **collaborating**. Git allows multiple developers to coordinate work on a project simutaneously. 

## What does Git do ?
- Git **manages** source code 
   
    - How is the source code managed ?
    - It is managed through **Repositories**.
      - A git repository is the .git/ folder inside a project. This folder is hidden. 
      - The git repsoitory tracks all the changes ever made to files in your project.
       - *If you delete the .git/ folder then you delete your projects history*
- **Clone** a project to work on a local copy 
- Control & track changes with **Staging** & **Committing**
- **Branches** & **Merge** to be able to work on different features or parts or versions of a project 
- **Pull** the latest version of a project to a local copy 
- **Push** local updates to the main project
- **Commit** files after each change 
  - Commit can be seen as snapshots in time. *Individual changes to  files, that allows us to see what changes were made when and by who. Always have a message when make a commit. 

  - WORKING DIRECTORY (Project) -----> STAGING AREA(index) -----> COMMITTED CHANGES 
      - **staging area in Git is stored locally on your machine.**
      - **committed changes are officcially saved to repositories history**
## Getting Started with Git for Mac users 
### 1. Download and Install Git from [git-scm](https://git-scm.com/download/mac)
### 2.   Under Binary Installer click on [installer](https://sourceforge.net/projects/git-osx-installer/)
### 3.  Then click on Download 
### 4.   Open file after downlaoding
     - **For mac users Message on the screen will say git was blocked**
     - Watch [Youtube video](https://www.youtube.com/watch?v=O3vtpZgI0fQ) to see how to unblock git and use gitBash on the terminal 
### 5. Check your version of Git on your machine

 ```
    git --version   
```

### 6. Let Git know your name and email 
     - Create an account on [Github](www/github.com)
     - In your terminal configure your name and email so Git knows which name and email to associate with that commit.
        - **In other words you are telling Git who you are**

  - #### Use global to set the name to be the same for every repository 
   ```bash
    git config --global user.name "Your Name"

    //replace "Your Name" with your actual name

    //keep the quotes 

   
  - #### Use global to set the email to be the same for every repository 
    
    git config --global user.email "your.email@example.com"

    //replace "Your.email@example.com" with your actual email

    //keep the quotes 
  
      - Setting a new username for a specific repository:
      - Remove the word ```--global``` if you want to change the name or email for a specific repository:

   
    - #### New Name
    
    git config user.name "Your New Name"
    
    
    - #### New Email
  

    git config user.email "your.new.email@example.com"
    
     ### Why would you not use global ?


      - #### Developers might want to omit the global setting, ```(--global)```, and configure specific settings for a particular repository due to a few reasons:
        - You might want your personal projects to use one identity while your work-related repositories use another. 

        -  Working on projects across various teams or organizations might require different identities
   
### 7. Create a Project to work in 
    - If you already created a folder to work in for your prject then naviagte it to it using the terminal. 
   
    # make a new directory if you have not created a folder 

    mkdir your_folder_name
  ```

    # change directory 

    cd your_folder_name
    
### 8. Initilize Git

```bash
git init  
```
- The git repsoitory is initialized. This will be an empy git repository
- Git creates a hidden folder  called ```.git``` to keep track of the changes
    


    #### Bonus: How to show the folder in vs code 
- Click on settings
- In search Settings type Exclude to find the default Exlcude list 
- Edit ".git" extension to "```.git-s``` " from the list  -> this will allow the .git folder to be visible ad no longer hidden

### 9. Open text editor and add some files

- There is a shorcut to open current working directory in visual studio code
```bash 
#this command will open visual studio code from the terminal
code . 
```
 - Note: This command ```code .```  may not nork if the code command is not recognized or added to your system's PATH.
 - Use [Resource](https://docs.newrelic.com/docs/style-guide/writing-docs/writer-workflow/set-up-local/#:~:text=Press%20command%20%2B%20shift%20%2B%20p%20to,that%20file%20in%20VS%20Code.) to assist if you run into this issue 
    
### 10. Working with Files
```bash
#create a new file (you can create files inside integrated terminal in visual studio code, make sure you are working in the bash temrinal)

touch "file_name" 
# example touch index.html creates html file 
```

### 11. Check Status of Repository

```bash
#check status of git 
git status

#check status with shorten output
git status --short

#Short Status flags are: 
    # ?? - Untracked (U), These are files that are present in your project directory but haven't been added to the Git repository.
    # A - File are added to stage 
    # M - Modified
    # D - Deleted files 
```
 ### 12. Staging our Files

```bash
#add our files to the staging enviorment
git add file_name

#or add multiple files at once 
 git add .

 or 

 git add -all
```
#### Notes: 
 - **Untracked Files:**
    -  These are files that are present in your project directory but haven't been added to the Git repository.
     - Git doesn't recognize these files and doesn't track changes in them.
    - They won't be included in commits until you explicitly add them to the staging area.

-   **Modified  Files:**
    -  These are files that have been changed since the last commit.directory but haven't been added to the Git repository.
     - Git recognizes these files as part of the repository and tracks the changes made to them.
    - They're in the working directory and are marked as modified because they've been edited **but not staged for a commit.**


-   **Added Files:**
    -  These are files that have been modified and then explicitly added to the staging area (using ```git add```).
     - Git recognizes these files as part of the repository and tracks the changes made to them.
    - They're in the working directory and are marked as modified because they've been edited **but not staged for a commit.**
 

 ### 13. ### Committing our Files 
- moving from staging to commiting files
- Adding commits keeps track of our progress and changes, as we work 
- In Git each commit is seen as a snaphot of our project. We can use these snapshots to revert to earlier versions when we need to. 

```bash
git commit -m "message"

git commit -am "message" 
#add and commit at the same time
 ```

13. ### Commit Log 

```bash
#git log allows us to see all of the commits that were made in the project

git log 

# see commits for that specific file 
git log <file_name>

#Git shows the commit history for the specified file, along with the differences (patch) for each commit. 
git log - p <file_name>


#command shows the revision and author information for each commit in a file
git blame <file_name>

```

14. #### Getting Help 
```bash 
#git help gives us a list of common Git commands used in various situations:
git help

#gives us all git commands
git help - a;

# it shows you the differences between what's in your files right now and what Git knows about. 
git diff 
```
```bash
esc key : wq click enter 
#to escape anf get back to terminal

```

## Gitignore Files 
- In Git, the .gitignore file tells Git which files or directories to ignore when tracking changes in a project.

# Developing a Project 
 - When working on projects it is important to know how git works. Especially, when collaborating with other developers.

 ### 1. Creating a Branch 
  - Think of a **branch as an independent workspace where you can add, modify, and delete files without affecting the files in other branches.**
 
  - It is reccomended not to work in the master/main branch. 
      - The master or main branch often represents the stable, deployable version of your project for most companies. 
      - Once your work is completed, tested, and reviewed, you merge it back into the master or main branch.
      - ***Changes made in one branch don't affect other branches until explicitly merged.***

      ![Branch Image ex:](img/branches_image.png)

      ```bash 
      #Lists all existing branches and highlights the current branch.

      git branch
      ```
      ```bash
      #Creates a new branch.
      git branch <branch_name>
      ```
      ```bash 
      #lists all the branches
      git branch -av
      ```
      ```bash 
      #swutching from one branch to another 
      git checkout <branch_ngit aame> 
      
      or 
      # Switches to a different branch.
      git switch <branch_name>

      #The git checkout command doesn't bring the changes from one branch to another directly. Instead, it switches your working directory and the state of your files to match the selected branch.
      ```
      ```bash 
      #When combined, git checkout -b <branch_name> allows you to create a new branch and immediately switch to that branch.
      
      git checkout -b <branch_name>
    ```
      - Creating a New Branch: -b flag is used to create a new branch and switch to it in a single step.
      
      - Switching Branches: The checkout command is used to switch between branches in Git.
      

## Merging Branches and Solving Conflicts 
- When multiple developers work on different branches or features simultaneously, merging allows these separate lines of development to come together

- If you merge festure into master and you have issues or bugs then it will go the master branch 

- Rememeber master/main branch is the clean branch. Want it to be free of conflict. (THERE SHOULD BE NO BUGS IN MASTER)

-Always merge master into your branch branch to reduce onflicts and chances of breaking website.


### How to merge barnches
1. Switch to the branch you want to merge into (e.g., main):
```bash 
git checkout branch
```

2. Merge the branch, after the word merge what ever branch you lister that this the brnach you are mergining into the other branch

```bash 
git merge branch

#EX: git merge master ----- >you are currently in feature branch. you are merging the master branch into the feature branch
```

# Merging Conglicts 

- Sometimes you may run into something called "CONFLICT" ang get a message like this on the terminal: 

```
Ex: "CONFLICT (content): Merge conflict in index.html. Automatic merge failed; fix conflicts and then commit the result."
```

- *** A merge conflict exists when Git cannot automatically merge changes from different branches into a single commit because these changes conflict with each other. ***

- A merge conflict arises when Git is unable to determine which changes to keep because both branches have made modifications to the same part of the file.

```bash 
imagine two people trying to edit the same sentence in a wor document at the same time. 

If both change different parts of the sentence, that's okay - Git can combine their changes. 

But if they both try to change the same word or phrase, Git gets confused. 

Ex: Lets say there is a group  project and two people chnage the first word of the sentence. Sam changes it to "First" and Dan chnages it to "Firstly",

It doesn't know which change to prioritize, and that's a merge conflict. You have to step in to decide which version of the sentence to keep or how to combine their changes manually.
```




```bash
<<<<<<< HEAD marks the beginning of the conflicting changes from the current branch.
======= separates the conflicting changes.
>>>>>>> incoming-branch marks the end of the conflicting changes from the incoming branch.
```








### Deleting a Branch
  - **When you are deleting a brnah you can not currently be in that branch !!!!**
```bash 
#This command deletes the specified branch. If the branch has already been merged into the current branch, Git will delete it.

#brnach has to be merged first to use this command
git branch - d <branch_name> 
```

```bash
#Forcibly deletes the specified branch, regardless of whether it has been merged or not. It's useful when you want to delete a branch regardless of its merge status.

git branch -D branch_name
```
       
    
      
# Github 
- Create Login 
- Create Repository 
- Name Repository 
- Decide to make public or private 
- Add READ.ME file or .gitignore file if one is not created already
- Push ```git push``` our local Repo to Github 

## How do we go from Github to Git 
- We are going to click on code 
- Clone the project
- Copy HTTPS link 
- Type ```git clone```then paste link 
  - make sure your repository is in the correct directory 
 
### Created By: @RiyaDevelops

 