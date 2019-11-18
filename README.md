# GitHub Classroom Guide for Students

This is a guide for you to setup Git and GitHub for use with GitHub Classroom. 

### Steps for getting setup with GitHub
1. Register for account on GitHub (https://github.com/) using your VCU email address. I recommend using a username that incorporates your VCU eID. If you already have a GitHub account, skip this step.

2. Complete this Google Form to record your GitHub username: https://forms.gle/GJSFoZW8EeYR7buh9

3. Install Git. 

4. Setup options in Git. If you are using a Mac, go to the terminal (Applications -> Utilities -> Terminal). Enter the three lines of code here, **changing the first two lines to your own name and email** (this should be the email associated with your GitHub account): 
   git config --global user.name 'Rodney Ram'
   git config --global user.email 'rram@vcu.edu'
   git config --global --list
 

### Steps for downloading and editing assignments from GitHub Classroom

1.  Have a folder specifically for your class (call it something like 256-fall-2019). 

    Note you can do this as you normally would with pointing and clicking, but you can also use the shell! This is good practice if you want to use Git outside of the class, as you normally have to use the Shell to interact with Git. Sean Kross has a great guide for using the shell here--http://seankross.com/the-unix-workbench/. However, I'll show you the basic steps you need.

 One thing that the shell does is allow you to navigate through all of your files by typing commands, rather than using your mouse. When you open up the shell, you can type `PWD`. This tells you the directory (folder) that you are in. You can also type `ls`. This lists the directories available to you. For example when I type `PWD`, the result is `/Users/debmduke/`. This tells me that I am in my own directory inside of my computer. When I type `ls`, I see directories such as Desktop, Documents, etc... I can also enter into a directory using the `cd` command. If I type `cd Desktop`, then I am now inside of the Documents directory. When I type `PWD`, the result is now `/Users/debmduke/Desktop`. I can go back to `/Users/debmduke/` by typing `cd ..`.

To make a directory (note I'm using directory and folder interchangeably here). Use the `mkdir` command. For example, to make a directory called 256-fall-2019, type `mkdir 256-fall-2019`. 
If you type `ls`, you'll now see `256-fall-2019` appear. 
You can then enter `cd 256-fall-2019` to go into the class-directory. 
Finally, to make a lab directory,  type `mkdir lab`. 

Here is a basic illustration of how my directory structure looks.

```
Users
│
│
│
└───debmduke
    │
    │
    │
    └───Desktop
        │
        │
        |
        |---256-fall-2019
            |
            |
            |
            |---lab
         

```

2.  You can access a link to the assignment through Blackboard. Note that after you accept an assignment for the first time, we will send you an invite to join the classroom organization as a member. Please accept this. You will probably get an email with the invitation, but you should also see a link at the top of your main GitHub page.

3. Enter the vcu-cmsc256-master repository on GitHub (this is online--GitHub is different from Git!). Click “Clone or Download”, and make sure it says “Clone with SSH” in bold in the top left of the pop-up box. If not, click on the blue “Use SSH” button on the top right of the pop-up box. Now copy the link in the box to your clipboard.

4. Navigate inside of your `lab` directory and then type `git clone repository-link` where `repository link` should be replaced with the link you copied to your clipboard in step 3. You now have the files.

    Note that if you received an error in the above steps, you may have to clone with HTTPS instead of SSH. You can do this by again clicking on the "Clone or Download" button in the repository page, then clicking "Use HTTPS" in the top right of the pop-up box. Now copy the link and repeat this step.
    
5.  After you make changes to the lab assignment, commit them.  Navigate to the lab directory. Type `git add -A`, and then `git commit -m "My commit message"`. `git add` is a command that tells git which files you want to record the changes to when you make your commit. For example, if I made changes to `file1` and `file2` since my last commit, I can choose to only commit (take a snapshot of) the changes I made to `file1`. `git add -A` says to add all of the files that have changed since the last commit. If I just want to add `file1`, I would instead type `git add file1`.

    Two things about committing. One, you should commit somewhat frequently. Two, leave informative commit messages. "Added stuff" will not help you if you're looking at your commit history in a year. A message like "Added initial version of hello-world method" will be more useful.

6.  At somepoint you'll want to get the updated version of the assignment back onto GitHub, either so that teachers/TAs can help you with your code, or so that it can be graded. You can do this by using a command called `git push`. 

### Obtaining and pulling a shared repository

Your classroom may have a repository where everyone in the class has access to it, such as a class materials repository (if you're in my class, we will have this). This repository will probably be updated throughout the class, and it will be useful to constantly have the most updated materials on your local computer. You can do this by first cloning the repository, and then pulling in changes. Here are the steps.

1. Clone the repository via command line. Read through step 1 in the previous section if you want a refresher about navigating with the command line. Remember, Mac users should use Terminal, and Windows users should use Git Bash. 
    In GitHub, navigate to the shared directory. Repeat step 3 from above, where we copy the link that we will use to clone this repository. If you get an error using SSH, you should instead use HTTPS. Go back to the command line and type `git clone repo-url` where the `repo-url` is replaced with the URL you just copied. If you type `ls`, the directory should now appear.
    
2. To pull in changes, navigate inside of this shared directory. To get the most recent version of this directory, you simply have to type `git pull`. If you get an error about merge conflict, don't freak out! This can happen if you edit locations in files that are also changed by a someone else. 

### Resources
* [The Unix Workbench](http://seankross.com/the-unix-workbench/)
* [Interactive learning guide for Git](http://learngitbranching.js.org/)
* [GitHub Guides](https://guides.github.com/)
