First creat a directory, then cd to the directory and type "git init". This initializes the directory as a master repository,

"git status" gives your the status of your repository and lists untracted files
 
use "git add" to add untracked files to be tracked by the repostory. This is kown as staging

you can create a file called ".gitignore" and add files that you do not want to be public in the ripository inside. For example;

 	$touch .gitignore   = this will create the .gitignore file
 
then create a file that for example has some password as follows
	$touch paswords.txt
The you can write some password in the paswords file and echo the paswords file into the .gitignore file
i.e; 	$echo "1234thg" >> paswords.txt
     	$echo "paswords.txt" >> .gitignore

The "git commit" command saves the staged file to the repository and using the -m you cam add comments to show what tchanges was made. e.g
	$git commit -m "modified the game changer"
	$git commit -a -m "commit all"

use the "git log" to view history of your commits

After commiting your changes, the next step is to push your changes from your locale repository (which is your laptop of desktop) to the Git server on a remote location (Such as GitHub)

The clone command is used to download a remote repository as follows;
	$git clone https://www.github.com/user/project_name.git
	cloning should be done at the very start of the project

If you have already initialized a local repository, you can connect it to the remote one using the following command
	$git remote add origin http://www.github.com/user/project_name.git

The push command pushes our committed changes to the remote repository, e.g
	$git push -u origin master (where origin is the name of our remote and the default local branch is master) The -u tells Git to remmember the parameters, so that next time we can simply run $git push and Git will know what to do. Note that you musn't push your work to remote if you want it private on your laptop.


the pull command pulls any changes made to the remote repository, either by you or by oher collaborators on the project to your local repository so you could be up to date with the most current version of the repository. e.g
	$git pull origin master
 
the "git diff" command checks what was different from our last commit
	$git diff HEAD


the "git diff --staged" command will show the changes you just staged

A stage can also be reset as follows;
	$git reset 'file-name' (meaning that all the changes will still remain in the file but no longer committed)

To reset the file to the latest committed version, the checkout command can be used;
	$git checkout -- 'filename'

The "git branch" command is used to create a new branch within the master repositiry; e.g
	$git branch branch-name

To switch to the branch, we use the "git checkout" command as follows;
	$git checkout branch-name

However, we can create and switch to a new branch at the same timw using the shortcut below;
	$git checkout -b branch-name

To see the lists of branches you have, run the git branch command in the project directory as below;
	$git branch

The "git commit --amend" command lets you modify the most recent commit. It lets you combine staged changes with the previous commit instead of creating an entirely new commit. it can also be usd to edit the previous commit message, for example;
	$git commit --amend -m "Donot modify the game changer"

