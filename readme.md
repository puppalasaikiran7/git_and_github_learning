Git hub and Git 

Theory
git is a software and github is the service where we can post 
this is a version control software which helps in tracking files for changes and in advance it helps in collaborating the projects too 
Repo or repository is a folder in the github which holds the complete software in it.


commands 

--> gh auth login ( this will login to the github account ) 
--> gh auth logout ( this will logout of the github account ) 
--> gh repo create repo_name --public  ( this will create the repo in the git hub and also gives the url ) 
--> gh auth status ( this will tell the status of the git hub login ) 


--> git config --global user.email emailid ( this will tell which email address to attach your commit too like which email id made the commit ) 
--> git config --global user.name username ( this will tell what name to attach to your commit like which person made the commit )

--> git --version ( this will show the version of the git software ) 
--> cd .. ( this is used to go back from the current folder to the parent folder ) 
--> cd tabkey ( after entering the cd and entering the tab will help in populating the files or folder in the current folder so that we can execute the command ) 
--> ls (list ) ( list of files and folders present in the current folder )
--> pwd ( present working directory ) ( prints the path of the exact folder we are in( current folder )  ) 
--> mkdir folder name ( creates the folder in the current directory or folder ) 
--> mkdir foldername1 foldername2 foldername3 ( this will create the multiple folders in current directory )
--> rmdir ( deletes the folder in the current directory or folder ) 
--> git status
	this will say three things 
		1) if the folder is being tracked or not 
		2) which branch you are on ( main or master ) 
		3) if there are any file that are not tracked those files are shown in red and which are tracked they are shown in green 

--> git init ( this will initialize the tracking of the folder ) 
--> touch filename ( this will create the file in the current folder ) 
--> rm filename ( this will remove the file from the current folder ) 
--> git add filename ( this will stage the file )
--> git commit -m message ( this will commit the file ) 
--> git branch ( this will tell which branch you are in ) 
--> git branch newbranchname ( this will create the new branch apart from the main branch ) 
--> git switch another branch name ( this will switch from one branch to another branch in the git )
--> git log ( this will say what are the commits done in that particular branch ) 
--> git log --oneline ( this will give the one line responses of the log's )
--> git remote -v ( this will give you the url links of the repo from the github ) 
--> git remote add origin url.git ( this will create the connection for the remote repo ) ( this is used if the github repo is created for the first time for that specific project )
--> git push -u origin branchname ( this will push the commits from the local file to github ) 
--> git push ( this will push the commit from local file to remote github , this can be used after the github short name is created and used for once like the above command ) 
--> git merge branchname ( be in the main branch and perform this and the branch that you want to merge will be merged in the main branch ) 
--> git branch -d branchname ( this will delete the branch ) 
--> git diff ( this will tell the difference in the file changes from the previous time ) 
--> git diff --staged ( this will tell the difference in the file changes which are staged from the previous time ) 
--> git checkout branchname ( this is used to reverting back to the past commit ) 
--> git rebase branchname ( this is used to temporarily remove the branch and attach it to the main branch ) 
--> git clone ( this is used to clone the repo ) 
--> git fetch ( this will just fetch the changes made by other person into our local system but does not merge it with the main branch ) 
--> git pull ( this will pull the complete repo from the git hub and merge into the existing working directory too ) 

Forking ( this is cloning other person repo into your github account if you want to contribute )
pull request ( after making changes in your local and pushing it to the git hub there will be a pull request which basically say if you want the author to add the changes that you made to their project then use this ) 


 



--> rm -rf .git ( this will remove the .git file which helps in tracking the folder , remove the tracking of the folder ) 

