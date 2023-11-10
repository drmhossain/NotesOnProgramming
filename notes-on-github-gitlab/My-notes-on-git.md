Notes on Git and Github

Things to Know:
Open file from Command prompt to vscode
start code <file_name> 
Open file from Command prompt/git bash within vscode
start code <file_name>   or  code <filename>

Some Essential Git Bash Commands:


* git init  
* git config --global user.name "user-name"
* git config --global user.name "user-email"
* git cofig list
* git status
* git add <file-name>
for all file
* git add --all or hit add .
* git commit -m "write msg for this commit"
* git log
* git log --oneline
* git diff
* git diff --staged
git diff master feature    : This command will output a list of all of the files that have been added or modified in the test branch since the master branch.
to reverse/erase the change/s
* git checkout <commit_number shown in log>
* git checkout <number shown in master br end>
* git rm <file-name>       (remove file from every stage?)
* git reset HEAD <file-name>
* git remote add origin https://github.com/<username>/<repository>.git
* git push -u origin master







Resources:
Command prompt Tutorial
@Git Cheat Sheet.pdf
@Git Cheat Sheet2.pdf
Tutorrial on Git and Github Bangla
Add A GitHub Repository To Your Local Machine





Articles on Git and Github:
My notes/Cheat Sheet on Git and github:
1. mkdir repo && cd repo
2. git remote add origin /path/to/origin.git
3. git add .
4. git commit -m "initial commit"
5. git push origin master
====================
Git Branch:
git branch // will show existing br name
git branch <file name>//create br
git checkout <file name>//move to the br
git checkout -b <file name>// create br with move to the br
==================
update local branch with repository branch ie, remote br:
in the cmd prompt -
1. >git checkout <branch name>  //promt will make the branch current
2. >git fetch
3. >git reset --hard origin/<remote branch name>


## GITHUB-GITLAB INTIGRATION/ USE BOTH FOR SAME REPOSITORY/PROJECT:
* ref: https://steveperkins.com/migrating-projects-from-github-to-gitlab/
Option 1: Create Separate Named Remotes
If you would like to encourage public contributions to your project, both from GitLab and GitHub, then you’ll want to create separate named remotes for each.  If GitLab is your primary host, then you would add a remote for GitHub like this:


git remote add github https://github.com/user/repo.git


Now, you can interact with GitLab or GitHub specifically.  You know that “origin” name, that 99% of git users type without thinking about it?  Well, that refers to your primary host, GitLab.  This new “github” remote name refers to GitHub (and you’re free to use any other name you like instead, it’s only for human-readability).


To push changes to either repository, use:


git push origin <branch>   (GitLab)
git push github <branch>   (GitHub)


You would pull down changes in similar fashion:


git pull origin <branch>   (GitLab)
git pull github <branch>   (GitHub)


As you do work on your GitLab primary host, you would just periodically update the GitHub mirror by pushing the “master” branch there.  Conversely, if someone in the community submits a pull request to your GitHub mirror, then the workflow would look like:


Review and merge the pull request on GitHub
Pull “master” into your local workspace
Push “master” to GitLab
This is definitely a bit more manual shuffling than you would have with a single remote.  However, it gives you maximum flexibility, and after a time or two it becomes automatic.


Option 2: Overload Origin with Both Remotes
Not every project seeks out public contributions.  Many of the projects on my GitHub account are basically “porfolio” items, there for resume purposes, and I specifically do NOT want pull requests.  If your project is a one-developer affair, then you can take a much simpler route to a GitHub mirror:


git remote set-url –add origin https://github.com/user/repo.git


You don’t see this trick everyday, but in git the relationship between a remote name and remote URL is not necessarily one-to-one!  Git will quite happily map a remote name to multiple repository URL’s.  Here, we’re overloading the default “origin” name to reference both GitLab and GitHub.  So the normal…


git push origin <branch>
git pull origin <branch>


… will push to (or pull from) both your primary GitLab host and your GitHub mirror!


This solution may be a little TOO clever for large team situations, but for projects on which you’re the sole developer it is probably the most convenient way to 


## git command line application
* https://cli.github.com/


## gitGIT RESOURCES:
- https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud
 - https://www.freecodecamp.org/news/best-git-tutorial/
 - http://git-scm.com
 - https://ohshitgit.com/





Add A GitHub Repository To Your Local Machine
####In your favorite web browser (all users)
Go to your profile on github.com
Click on "Repositories"
Click "New" towards the top-right of the screen
Give your repository a name. Avoid spaces and silly characters
Give your repository a description. Be as descriptive as you can, explain the purpose of the repository
Set your repository to "public" or "private," I suggest public unless required to keep with the spirit of GitHub
Check the "Initialize this repository with a README" box unless you have already run git init in a directory via Terminal
If you know you want to ignore a specific code language, select it in the "Add .gitignore" dropbox, we can add specific folders and files to this later on
Give your repository a usage license. I suggest looking at this site; I prefer the MIT license
Click, "Create repository"
Clone your repository to your local machine
If you use the GitHub app
Open the GitHub app and make sure you are logged into your account using GitHub > Preferences, select "Accounts" and then enter your GitHub username and password, then click "Sign In"
Back in your browser, click on the "Clone in Desktop" button. It will automatically take you to the GitHub app and ask where you would like the repository cloned to
Choose the location and directory name for your local repository and click "Clone"
You can now right-click or control-click the name of your repository from the left sidebar and choose "Open in Atom" to quickly get to work
If you use terminal
On this new page (URL should be github.com/username/repo-name) find the SSH clone URL in the right menu and click the "Copy to clipboard" button. If it says "HTTPS clone URL" above the input box, click on the blue "SSH" link below, this will change the clone URL to use SSH instead of HTTPS, and then click on the "Copy to clipboard" button
####If using the GitHub app
Open the GitHub app and make sure you are logged into your account using GitHub > Preferences, select "Accounts" and then enter your GitHub username and password, then click "Sign In"
Your local repository should already be created (see above steps)
If you have worked on this project on another computer it is wise to push the "sync" button at the top-right before doing any further work on your current machine
Once your files have been edited you will need to add, commit, and sync those changes. There will be a list of files in the center column that, when highlighted, will show what has been changed in the preview window on the right. Select the files that you would like to add to a commit by checking the checkboxes to the left side of the file name.
Add a summary and a description for each commit, andinitgit then push the "Add to [branch name]" button.
Once all of your files have been committed, you can sync your repository by clicking the "sync" button at the top-right
Rejoice in all the GitHub simplicity
####If using Terminal
Move to the parent directory where you would like to clone your new GitHub repository. You will use a "/" to move deeper into your folder structure. If you have spaces in your folder names you will have to put a "" before them, like so: cd ~/School/HCC/Spring\ 2015/ART229/Projects. Note: It's quicker, easier, and less confusing if you can avoid using spaces in your directory names as much as possible (but not always possible)
Clone your GitHub repository to a new directory. There are two main ways to do this:
Create the new project repository as you are cloning your repository.
Run git clone git@github.com:username/project-name.git new-project-name you can paste your SSH clone URL in to replace the "git@github.com..." business and avoid any typo errors. You can also leave off the "new-directory-name" in which case your new directory's name will be the same as your GitHub repository's name when you created it. When (if) you designate your new directory's name in the clone command, you can use the same "" character to add a space to name, e.g. git clone git@github.com:username/project-name.git New\ Project\ Name
Note: If you get an error message about your directory already being a GitHub repository, you can change the remote URL by running git remote set-url origin git@github.com:username/project-name.git. This will change which remote repository your local machine points to when running git pull and git push. Avoid this if you can when just starting off. If you do this you will also have to do the following:
Run git fetch
Run git pull origin master. You will likely have merge conflicts, in which case you will have to open the specified files and edit them and then save them.
Run git add [name of file] e.g. "git add index.html" or run git add --all to add all changes to all files to your commit.
Run git commit -m "Write a message about your commit here"
Repeat the previous two steps until all files have been added and committed
Run git push origin master to push your changes to the remote repository.
Create a new directory where we can clone our GitHub repository into before cloning.
Create the new directory in your parent folder. You can use the same "" character before any spaces in your folder name, like so mkdir Project\ 1-Profile\ Page
Move into your new directory, cd Project\ 1-Profile\ Page
Run git clone git@github.com:username/project-name.git . and DO NOT forget the "." at the end. That "." represents the current directory (the one we just made and moved into), which tells GitHub to clone our repository into the directory that we're currently in
Open your repository in your favorite text editor open -a "Atom" . (note the "." again) and get to work!
Once you've edited your files you will need to add and commit them. Run git add [name of file] e.g. "git add index.html" or run git add --all to add all changes to all files to your commit.
Run git commit -m "Write a message about your commit here" 1.Repeat the previous two steps until all files have been added and committed
Run git push origin master to push your changes to the remote repository.
Rejoice in all of your GitHub mastery.



Useful git command:
set a name that is identifiable for credit when review version history
git config - -global user .name "[firstname Lastname]"
set an email that is identifiable for credit when review version history
git config  - -global user . email "[valid-email]"
initialize an existing directory as a Git repository
git init
Retrieve an entire repository from a hosted location via URL
git clone [repository url]



Repository Link:
The GitHub Pages repository URL is always https://{userid}.github.io/{reponame}
To see in command prompt without pulling remote repository:      
git ls-remote https://github.com/drmhossain/NotesOnProgramming
    Here :
userid is  drmhossain
Repository name is  NotesOnProgramming    
Connect remote repository with local repository
git remote add origin <repository url> 

Find url on gitgub code page. Press green code button - it will show url for that repository.
git remote
will show the added ‘origin’
Now one can use ‘origin’ against <repository url>

git remote -v
will show where it is connecting in the repository
git clone vs add
git remote add
 just creates an entry in your git config that specifies a name for a particular URL. You must have an existing git repo to use this. git clone creates a new git repository by copying an existing one located at the URI you specify.
Make directory
Create directory
          mkdir <folder_name>
Create file in directory
         touch <file_name>
Open file
         open <file_name>

Remove file from local directory
rm -rf <file_name>          
   
 Move directory to other  directory
git mv <this directory will move> <to this directory>         

 Move file to other  directory
git mv <file> <new_directory>   
Command prompt
Make directory/folder
mkdir <directory_name>
delete directory 
rm -rf <directory_name>
if directory not empty
rmdir /s <directory_name>

Changed directory from C:drive to D
cd /d D:\

Create file
echo > index. html
or
type nul > index2.htm1
Delete file
del index. html

Open file
<file_name.ext>
Write in a file from cmd prompt
echo <write whatever you want> > <file_name.ext>
exam: echo this is my text > myfile.txt
This will write this is my text in file name myfile.txt
Read file
type <file_name.ext>

Similar commands Cheat Sheet between git bash and command prompt cli:
Git Bash
Command Prompt
cd
cd
ls
dir
pwd
echo %cd%
mkdir
mkdir
rmdir
rmdir
touch
touch
cat
type
grep
findstr
more
more
less
less
head
head
tail
tail
sort
sort
uniq
uniq
grep -v
findstr /v
xargs
for /f
echo
echo
exit
exit


Appendix:

GIT COMMANDS
GIT BASH NAVIGATION

Ctrl+L or clear
clear screen

Clrt+` (back tic)
focus to terminal from vscode file screen 

How do I exit insert mode in git?
To edit, 
 type   "i"     
to switch to insert mode. 


To leave insert mode,
 hit     ESC     key


To save and quit, type
   :wq          and press  Enter key   
don’t forget to write colon(:)
which means "write, quit". 




GIT REPOSITORY SETUP 
Configuring user information used across all local repositories 
git config --global user.name "[firstname lastname]" 
set a name that is identifiable for credit when review version history 

git config --global user.email “[valid-email]" 
set an email address that will be associated with each history marker 

git config --global color.ui auto 
set automatic command line coloring for Git for easy reviewing 

SETUP & INIT 
Configuring user information, initializing and cloning repositories 
git init 
initialize an existing directory as a Git repository 

git clone [url] 
retrieve an entire repository from a hosted location via URL 

Note: In git bash If prompt show colon (:) in the last line (it shows after command “git log”
just press q in the keyboard to return to the regular prompt.


rm -rf <directory>
Delete a local directory

—------------------------------------------------------------
RENAME A FILE FROM GIT BASH
Open Git Bash.
Navigate to directory.
Use command: 
git mv oldfilename newfilename
Commit change: 
git commit -m "Renamed file"
Push changes: 
git push

—------------------------------------------------------------



STAGE & SNAPSHOT 
Working with snapshots and the Git staging area 

git status 
show modified files in working directory, staged for your next commit 

git add [file] 
stage a file. 
—-------------------------------
git rm --cached <file>
unstage a file.

git reset [file] 
unstage a file while retaining the changes in working directory 

The difference between git rm --cached file and git reset file is that 
git rm --cached file removes the file from the index, but does not remove it from the working tree. 
Git reset file, on the other hand, removes the file from the index and the working tree.
—-------------------------------
git diff 
diff of what is changed but not staged 

git diff --staged 
diff of what is staged but not yet committed 

This command will output a list of all of the files that have been added or modified in the test branch since the master branch.
git diff master feature   

 Git add -A 
A is shorthand for -all. stage all changed file in directory and subdirectories

 Git add . 
stage all changed file in directory but not subdirectories (don't forget to write ( “.” ) dot after “add”

git restore <file>
will restore all changes made

 Git add *.js 
(directory wildcard)

 Git add **/*.js 
(directory & subdirectory wildcard)

git diff
Checking the difference: 

git commit -m "[descriptive message]" 
commit your staged content as a new commit snapshot 

git commit -am "[descriptive message]" 
 or 
git add . && git commit -m "[descriptive message]" 
together staging and commit 

git show <commit_id>    or git show or git show HEAD
To show details of commits

UNCOMMITE
• If all you want to do is undo the act of committing, leaving everything else
intact, use:
git reset --soft HEAD^

• If all you want to do is undo the act of committing, and also removing from the
stagging area:
git reset HEAD^
• And if you actually want to completely undo it, throwing away all
uncommitted changes resetting everything to the previous commit (as the
original question asked':
git reset --hard HEAD^

DELETING MULTIPLE COMMITS WITH SINGLE COMMAND
git reset -soft HEAD-4
git reset -soft HEAD-3

git revert
TBR

git clean
TBR

git rm
TBR

—-------------------------
GIT REMOTE / GIT REMOTE CONNECTION

git remote
Shows the remote connection.

git remote -v
shows the remote along with the url


git remote add <name> <REMOTE_URL>
it will connect local repository with remote repository
Example: git remote add origin https://github.com/anisul-lslam/life-story.git
Here: <name>=origin  usually most of the time name as ‘origin’ is used. but you can use any name.



create a new remote repository from an existing local repository: ?
Create a bare repository on the remote side:
Type git init --bare
Add the remote side as the push/pull tracker for your local repository:
Type git remote add origin URL
Locally, type git push origin master
You can also create a new repository from an existing project by: 
Going into the directory containing the project
Typing git init
Typing git add to add all of the relevant files
Typing git commit
You can also add an existing project to a Git repository by: 
Committing the files that you've staged in your local repository
Copying the remote repository URL field from your GitHub repository
Adding the URL for the remote repository where your local repository will be pushed

ref: Add Existing Project To Git Repo - GitHub Gist
—-------------------------------------------------
CREATE A NEW REMOTE REPOSITORY FROM LOCAL DIRECTORY/REPOSITORY/ MACHINE  ?😰

If you want to create a remote Git repository on GitHub without associating it with a GitHub account, you can use GitHub's REST API to programmatically create a repository. Here's a high-level outline of how you might do it using cURL and the GitHub API. You would need to replace the placeholders with your actual values:

1. **Generate a Personal Access Token**: You need to create a Personal Access Token on your GitHub account with the necessary permissions (such as "repo" and "admin:public_key") for the GitHub API to work. You can create a token in your GitHub account settings.

2. **Use cURL to Create the Repository**:

curl -H "Authorization: token YOUR_ACCESS_TOKEN" \
     -d '{"name": "your-repo-name", "description": "Your repository description"}' \
     https://api.github.com/user/repos

Replace the following:

- `YOUR_ACCESS_TOKEN` with your GitHub Personal Access Token.
- `your-repo-name` with the desired name for your repository.
- `"Your repository description"` with the description for your repository.

This cURL command sends a POST request to the GitHub API to create a new repository under your GitHub account programmatically. The repository will be created without visiting the GitHub website.

Please note that you should use this approach with care and ensure that your access token is kept secure. Also, be aware of any usage limitations or terms of service provided by GitHub or any other Git hosting service you might use.
—---------------------------------------------------------
GIT PUSH
The difference between git push and git push u origin main is that git push will push all of the branches in your local repository to the remote repository, while git push u origin main will only push the branch that is currently checked out.
git push
This will push all of the branches in your local repository to the remote repository.
git push u origin main
This will only push the branch that is currently checked out to the remote repository.
branch may be main in focus or any other  branch on focus


GIT PULL
git pull

—---------------------------------------------------------

BRANCH & MERGE 
Isolating work in branches, changing context, and integrating changes 


git branch 
list your local branches. a* will appear next to the currently active branch 
git branch -r 
list your all branches in the remote repository

git branch [branch-name] 
create a new branch in local directory

git checkout -b <”branch name”>
Create and focus on a newly created branch with one command  ?

git push -u origin <local br name>
push a locally created branch in the remote repository
—------------------------------------------------------------------------------
Create and push branch from local repository
You cannot create a new branch directly in a remote repository from local repository. Instead, you must create a new local branch and then push it to the remote repository.
To create a new local branch in Git Bash, use the following command:
git checkout -b <branch-name>
This will create a new branch named <branch-name> and switch to it.
Once you have created your new local branch, you can start making changes. Once you are satisfied with your changes, you can push your branch to the remote repository using the following command:

git push origin <branch-name>

This will push your local branch to the remote repository named origin.
If you want to set the remote branch as the upstream branch for your local branch, you can use the following command:

git push -u origin <branch-name>

This will set the remote branch as the upstream branch for your local branch, which means that future git push commands will automatically push your local branch to the remote branch.
Here is an example of how to create and push a new branch in a remote repository from Git Bash:
Here is an example of how to create a new branch in a remote repository from Git Bash:
# Create a new local branch named and focus to that br:
git branch <branch name>
git checkout <branch name>
#Do the above two commands together:
git checkout -b <new branch>
git commit -m "Added branch <new branch>"(This is optional. Do it if you changes something need to commit)
# Push the local branch to the remote repository.
git push origin <new branch>
Once you have pushed your local branch to the remote repository, you can start collaborating with other developers on the feature.
—------------------------------------------------------------------------------
DELETE BRANCH
git branch -d <branch name>
to delete a branch. you can not delete it when it is the current branch.

git checkout -b <new_branch> <existing_branch>
To create a branch of another branch on git locally, you can use:
where:
<new_branch> is the name of the new branch you want to create
<existing_branch> is the name of the existing branch you want to create the new branch from

git checkout -b <”branch name”>
Create and focus branch with one command:

git checkout 
switch to another branch and check it out into your working directory 

git push origin <branch_name>
will create this branch in the origin of  remote repository

git merge <branch_name>
<branch> is the branch that is going to be merged with current focused branch
merge the specified branch's history into the current one 
During merge focus should be on the branch where data will come from any other branch

To find out how many branches are in the remote repository from git bash, you can use:
git branch -r | wc -l
This will count the number of lines in the output of the git branch -r command, which will be one line for each branch in the remote repository.
----------------------------------------
Delete a remote branch from your local repository, 
use the following Git command:

git push origin --delete branch-name

Replace "branch-name" with the name of the remote branch you want to delete. This command will remove the branch from the remote repository, which effectively deletes it from your local repository as well when you fetch or pull changes from the remote.

If you want to delete a remote branch without deleting it from your local repository, you can use:

git push origin :branch-name  

This will delete the remote branch but keep a copy of it in your local repository.

To delete a branch of a remote repository from your local repository, you can use:
git fetch origin
git branch -d origin/<branch>


----------------------------------------


INSPECT & COMPARE 
Examining logs, diffs and object information 

git log 
show the commit history for the currently active branch 

got log –oneline
will show log in one line summary 

git log branchB..branchA 
show the commits on branchA that are not on branchB 

git log --follow [file] 
show the commits that changed file, even across renames 

git log 

git diff branchB...branchA 
show the diff of what is in branchA that is not in branchB 

git show [SHA] 
show any object in Git in human-readable format 

touch <filename.ext>
create a new file

touch <some text> > <filename.ext>
add some text. WARNING: It will replace all previous text!

touch <some text> >> <filename.ext>
add some text in a new line.

OPEN FILE
To open a file in git, you can use the git show command. The syntax is:
   git show <commit>:<path>    
where:
<commit> is the commit you want to open the file from
<path> is the path to the file you want to open
For example,
    git show master:README.md   



SHARE & UPDATE 
Retrieving updates from another repository and updating local repos 
git remote add [alias] [url] 
add a git URL as an alias 

git fetch [alias] 
fetch down all the branches from that Git remote 

git merge [alias]/[branch] 
merge a remote branch into your current branch to bring it up to date 

git push [alias] [branch] 
Transmit local branch commits to the remote repository branch 

git pull 
fetch and merge any commits from the tracking remote branch 

TRACKING PATH CHANGES 
Versioning file removes and path changes 

git rm [file] 
delete the file from project and stage the removal for commit 

To remove all directories in git locally, you can use:
git rm -r --cached .
This will remove all directories in the current directory and add them to the index. To remove the directories from the filesystem, you can use:
git commit -m "Removed all directories"
git push
This will remove all directories from the filesystem and push the changes to the remote repository.

—--------------------------------------------------------------------
Delete .git from a local repository 
is a bit more complicated than just deleting the files in the repository. First, you need to make sure that you are in the directory that contains the repository. Once you are in the correct directory, you can use the following command to delete the repository:
rm -rf .git
This command will delete the entire .git directory, which contains all of the files and data associated with the repository. Once the directory is deleted, the repository will be gone and cannot be recovered.
It is important to note that deleting a local git repository will not delete any of the files in the repository. If you want to delete the files as well, you will need to use a different command. For example, you can use the following command to delete all of the files in the repository:
rm -rf ./*
This command will delete all of the files in the current directory, including any files that are in subdirectories.
It is also important to note that deleting a local git repository will not delete any of the history of the repository. The history of the repository is stored in the .git directory. If you want to delete the history of the repository, you will need to use a different command. For example, you can use the following command to delete the history of the repository:
git filter-branch --prune-empty --index-filter 'git rm --cached --ignore-unmatch <file>' HEAD
This command will delete all of the files in the repository that are not tracked by git. It will also delete the history of the repository.
It is important to note that deleting a local git repository is a destructive operation. Once you delete a repository, there is no way to recover the files or the history of the repository.
—--------------------------------------------------------------------
SSH KEY GENERATION FOR GIT
Connect to GitHub:
We need to create the key-pair of SSH using the command:
ssh-keygen -t rsa -C "YOUR_EMAIL_ADDRESS"



Here, YOUR_EMAIL_ADDRESS is your email id associated with your GitHub account.
Log in to GitHub:
Log into your GitHub account using the command:
ssh -T git@github.com
—-------------------------------



Git move folders
git mv [existing-path] [new-path] 
change an existing file path and stage the move 

git log --stat -M 
show all commit logs with indication of any paths that moved 

IGNORING PATTERNS 
Preventing unintentional staging or commiting of files 

Logs/ *.notes 
pattern*/ 
Save a file with desired patterns as .gitignore with either direct string matches or wildcard globs. 

git config --global core.excludesfile [file] 
system wide ignore pattern for all local repositories 

REWRITE HISTORY 
Rewriting branches, updating commits and clearing history 

git rebase [branch] 
apply any commits of current branch ahead of specified one 

git reset --hard [commit] 
clear staging area, rewrite working tree from specified commit 

TEMPORARY COMMITS 
Temporarily store modified, tracked files in order to change branches 

git stash 
Save modified and staged changes 

git stash list 
list stack-order of stashed file changes 

git stash pop 
write working from top of stash stack 

git stash drop 
discard the changes from top of stash stack 

—------------------------------------------------------
To delete a remote (unstaged) repository file from git bash terminal, you can use:
git rm --cached <file>
git push origin <branch>
—----------------------------------------------------


—----------------------------------------------------------------
To exit Vim in the terminal, you can: 
Press the Esc key.
Type :q and hit Enter.
If you have made changes and need to save them, use :wq to save and quit.
If you want to exit without saving your changes, use :q! .
If normal quit has failed, you can force quit by pressing the escape key multiple times until you're sure that you're not in insert or command-line mode anymore. Then type ":q!" followed by enter key.
—----------------------------------------------------------------

Basic nano text editor  commands in terminal: 
Open file: $ nano <file> $ nano ^R <file>
Save as: ^O
Quit: ^X
Undo/redo: M-U M-E
Cancel nano command: ^C
Next search result: ^W
Find and replace: ^\ A
Regular expressions: ^W M-R ^\ M-R
Here are some navigation shortcuts: 
Move forward one character: Ctrl+F (^F)
Move back one character: Ctrl+B (^B)
Move forward one word: Ctrl+Space (^Space)
Move back one word: Alt+Space (M-Space)
Move to the previous line: Ctrl+P (^P)
Move to the next line: Ctrl+N (^N)
Move to the next page: Ctrl+V (^V)

—------------------------------------------------------------------------------------
 command ssh -T git@github.com is used to establish a secure shell (SSH) connection to GitHub. 
SSH is a network protocol that allows you to securely connect to a remote server. It is more secure than other protocols, such as HTTP, because it encrypts all data traffic between your computer and the server.
The -T option tells SSH to allocate a pseudo-terminal to the process. This is necessary for some Git commands, such as git clone and git push.
The git@github.com part of the command specifies the hostname of the remote server that you want to connect to. In this case, it is GitHub.com.
To use this command, you will need to have an SSH key pair configured on your local machine. You can generate an SSH key pair using the ssh-keygen command. Once you have generated an SSH key pair, you will need to add your public SSH key to your GitHub account.
Once you have added your public SSH key to your GitHub account, you can use the ssh -T git@github.com command to connect to GitHub. If you are prompted to verify the host key, type yes to continue.
Once you are connected to GitHub, you can use Git commands to clone and manage your repositories.
Here is an example of how to use the ssh -T git@github.com command to clone a repository:
ssh -T git@github.com git clone https://github.com/user/repo.git

This will clone the repository repo from the user user's GitHub account to your local machine.
You can also use the ssh -T git@github.com command to push changes to a remote repository:
ssh -T git@github.com git push origin main

This will push the changes on your local main branch to the origin remote repository.
Using SSH to connect to GitHub is more secure and efficient than using other protocols, such as HTTP. If you are using Git regularly, it is recommended that you configure SSH on your local machine.
—--------------------------------------------------------------------------------------------------
# Correcting paste error in git bash terminal  (it adds “ ^[[200~<actual copied texts>~ “ with the actual copied text)
  git config --global core.autocrlf input    
—------------------------------------------------------------------------------------------

How to push in the remote branch:
To push a file to a remote branch with Git Bash, follow these steps:
Open Git Bash and navigate to the directory of the file you want to push.
Add the file to the staging area:
git add <filename>
Commit the file to the local repository:
git commit -m "<commit message>"
Push the local commits to the remote branch:
git push origin <branch name>
For example, to push a file named myfile.txt to the remote branch master, you would run the following commands:
git add myfile.txt
git commit -m "Added myfile.txt"
git push origin master


If you are pushing to a remote repository for the first time, you will need to add the remote repository as a remote. To do this, run the following command:
git remote add origin <remote repository URL>
Replace <remote repository URL> with the URL of the remote repository.
Once you have added the remote repository, you can push your local commits to the remote branch using the
 git push command.
Example:
git remote add origin https://github.com/your-username/your-repository.git
git push origin master
This will push all of the local commits on the master branch to the remote master branch.
Note: To push a file to a specific branch, replace <branch name> with the name of the branch you want to push to. For example, to push the file to the develop branch, you would run the following command:
git push origin develop
Safety guidelines:
Make sure that you are pushing the file to the correct branch. Pushing a file to the wrong branch can overwrite existing code and cause problems.
Make sure that you have committed the file to the local repository before pushing it to the remote repository. This will help to prevent accidental changes from being pushed to the remote repository.
If you are pushing the file to a shared repository, make sure that you have permission to push to that repository.


To delete all files in the master branch of a local repository using Git Bash, follow these steps:
Checkout the master branch:
git checkout master

Delete all untracked files:
git clean -f -d

Force-delete all tracked files:
git rm -rf --cached .

With interactive way:
git clean -i

      5. Commit the changes:
git commit -m "Deleted all files in master branch"

To read a file in bash:
cat <filename>

—-------------------------
git merge
There are a few reasons why the git branch command might show a branch as already merged with the master branch in your local repository:
The branch has actually been merged with the master branch. This is the most common reason. Once a branch has been merged with the master branch, it is no longer needed, and you can safely delete it.
The branch is a remote-tracking branch that has been merged with the remote master branch. Git creates remote-tracking branches automatically when you clone a remote repository. These branches track the remote branches on the origin repository, and they are updated whenever you fetch or pull changes from the remote repository. If a remote-tracking branch has been merged with the remote master branch, it will still show up as a merged branch in your local repository, even if it has not been merged with your local master branch.
There is a merge conflict that is preventing the branch from being merged with the master branch. If you have made changes to the master branch since you last merged the branch, Git will try to merge the two branches when you try to merge the branch again. However, if there are any conflicting changes, Git will not be able to merge the branches, and the branch will show up as a merged branch.
To check if a branch has actually been merged with the master branch, you can use the
 git branch --merged
 command. This command will list all of the branches that have been merged with the current branch. If the branch is listed in the output of this command, then it has been merged with the master branch, and you can safely delete it.
If you are not sure why a branch is showing up as a merged branch, you can use the 
git log --merges 
command to see the history of merges that have been performed on the branch. This command will show you all of the merges that have been performed on the branch, including merges with the master branch and merges with other branches.
Here are some additional things to keep in mind:
If you delete a local branch that has not been pushed to the remote repository, the branch will still exist in the remote repository. To delete the branch from the remote repository, you will need to force push the branch.
If you delete a remote-tracking branch, you will need to recreate it if you want to continue tracking the remote branch.
If you are having trouble merging a branch with the master branch, you can try resolving the merge conflict manually or using a merge tool.
—------------------------------------------

PROTECT A BRANCH
To prevent from deleting your important branches that containing version copy in git, you can use the protected flag. To do this, you need to use the git branch --protected command. The syntax is:

git branch --protected <branch>

where:
<branch> is the name of the branch you want to protect
Once you have protected a branch, you will not be able to delete it using the git branch -d command. You will need to use the

 git branch -D command to delete a protected branch.

—------------------------------------------------
push a local repository to create a brand new repository without visiting the GitHub website. 
To do this, you will need to use the Git Bash command line tool.
Open Git Bash.
Navigate to the directory containing your local repository.
Run the following command:
git remote add origin <remote_repository_url>

Replace <remote_repository_url> with the URL of the new remote repository that you want to create.
Run the following command:
git push origin master

This will push your local repository to the new remote repository.
Here is an example of how to use the Git Bash command line tool to push a local repository to create a brand new repository:
 git remote add origin https://github.com/my-username/my-new-repository.git
 git push origin master

These commands will create a new remote repository called my-new-repository on GitHub and push the master branch of your local repository to the master branch of the remote repository.
Once you have pushed your local repository to the new remote repository, you can visit the GitHub website to view your new repository.
—---------------------------------------------------------------------------








