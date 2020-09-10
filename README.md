# GithubTutorial
Notes on git commands for easy understanding

//If you are joining an ongoing project and you are new to the project use clone Command
$-  git clone <repourl>//1

//If you are starting a very new project use init to create a new repo
$-  git init //1

Git Repository New Branch Creation:

$-  git branch  //check the exsisting branch.7(a)
$-  git branch <branchname>  //create a new branch.7(b)
$-  git checkout <branchname>  //switch to the new branch.7(c)

//Add origin for proper connectivity between local and central repo.
// We call remote repo as origin. this is for sync purpose
$-  git remote add origin "https://github.com/PreDestin/GithubTutorial.git" //2

//pull cmd pulls all the new or modified files from central repo
//and directly connects with the master branch.
&-  git pull origin master//3

//fetch cmd does the same as pull but it does not connect to the master
//rather it places the fetched files in some other branch. So we have to merge
//to see the changes in your local repo.
$-  git fetch // git pull = git fetch + git merge

//There is an intermediate between the workspace and the local repo
//where the changes you make to the local repo by commit command are indexed.
//And to add the untracked files to the index use add cmd.
$-  git add <filename>//4(b)
$-  git add -A//To add multiple files to the index at once.4(c)

//To see list of files in the index use status
$-  git status//4(a)

//after all the changes are made commit to local repo
$-  git commit -m "Commit message for others to understand"//5(a)
$-  git commit -a -m "Commit changes"//To commit multiple files at once.5(b)

//To see how git stores all the commits use log command
$-  git log//6

//merge the branches to the master branch. First come back to master branch and
//use merge command.
$-  git checkout master  //7(a)
$-  git merge <branchname>  //7(b)

//rebase cmd does the work of merge cmd and reduces the number of branches,
//gives cleaner code and linearity is promoted
$-  git checkout <branchname>  //8(a)
$-  git rebase master  //8(b)

//If I don't want the changes made in local repo to reflect in mater branch of
//central repo and to keep that in a separate branch in central repo.Use below cmd
$-  git checkout <branchname>
$-  git push origin <branchname> //origin is the remote or the central repo.
//After making all the necessary changes do push to the central repo.
//Don't make frequent changes as it may affect other contributors works


//To revert back changes. Take hexa code from git log
$-  git checkout <8bithexadeccode> <filename> //8
