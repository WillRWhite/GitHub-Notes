### General Git Stuff

### Initial git setup:  
git config --global user.email "william.white@directinsight.co.uk"  
git config --global user.name "William White"  
git config credential.helper store  

#### Configure Local Repo

git init  
git add .  
git commit -m "First commit"  

#### Push Local Repo to this Remote Repo

git remote add origin https://github.com/WillRWhite/holidayhomes.git  
\# Check where origin is located:  
git ls-remote --get-url origin  

\# Verifies the new remote URL  
git remote -v  
git push -u origin master  

#### Clone

git clone https://github.com/WillRWhite/holidayhomes.git  

#### Synchronising Local Repo with this Remote Repo

git status  
\# Synchronise changes only  
git fetch origin  
git status  
\# The following two commands are only required if you have made changes to the local repo  
\# git reset --hard origin/master    
\# git clean -f -d  
\# now if required merge the changes  
git merge origin\master  
\# The following commands fetches and merges  
git pull  

### Taging the last commit and pushing to the remote  
Full details here https://git-scm.com/book/en/v2/Git-Basics-Tagging  
A basic annotated tag:  
git tag -a v1.4  
git tag  
git show <tag>  


#### To push a single tag:  
git push origin tag <tag_name>  
And the following command should push all tags (not recommended):  
git push --tags  


### Amending the last commit with a new or updated file 

git add <the_left_out_file>    
git commit --amend --no-edit  
The --no-edit flag allows to make an amendment to the commit without changing the commit message.

### Other Useful Resources

#### Interacting with a remore Repo

https://help.github.com/articles/fetching-a-remote/  
https://stackoverflow.com/questions/17712468/what-is-the-difference-between-git-remote-update-git-fetch-and-git-pull  
