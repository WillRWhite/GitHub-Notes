### General Git Stuff  

### Initial git setup:  
git config --global user.email "william.white@directinsight.co.uk"  
git config --global user.name "William White"  

#### Configure Local Repo  
git init  
git add .  
git commit -m "First commit"  

#### Push Local Repo to this Remote Repo  
\# Check where origin is located:  
git ls-remote --get-url origin  
git remote add origin https://github.com/WillRWhite/holidayhomes.git  
\# This will automatically store any GitHub credentials:  
git config credential.helper store  
\# Alternativvely add token to URL eg:  
git remote set-url origin https://<TOKEN>@github.com/WRWhite/PingTest.git
\# Also see:  
https://seankilleen.com/2021/01/how-to-force-git-to-prompt-you-for-a-password/  
https://stackoverflow.com/questions/14643308/how-can-i-force-user-and-password-prompt-when-pushing-to-my-git-repository  
https://git-scm.com/docs/gitcredentials  
https://www.saurabhmisra.dev/force-git-show-login-prompt/  



### Verifies the new remote URL  
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

### Deleting the last commit:  
https://stackoverflow.com/questions/448919/how-can-i-remove-a-commit-on-github:  
git reset --hard commit_hash_you_want_to_return_to  
git push --force  

### Moving a tag
https://stackoverflow.com/questions/8044583/how-can-i-move-a-tag-on-a-git-branch-to-a-different-commit  
To sum up if your remote is called origin and you're working on master/main branch:  
git tag -d <tagname>                     # delete the old tag locally
git push origin :refs/tags/<tagname>     # delete the old tag remotely
git tag -a <tagname> <commitId>          # make a new tag locally
git push origin <tagname>                # push the new local tag to the remote 

### Merging
\# Say you are on branch main and you want to expiriment with a new feature, then first ensure you main branch is comitted and pushed, then you can create a new branch eg test:  
git branch test  
\# Then switch to that branch  

Update as required including release_notes if you will eventually merge this branch back to main etc  
git commit
\# Add a tag (with the release version if required)
git tag -a vn.m  
\# Push including tags to origin  
git pusg –tags  
\# Do a git status and log to check everything cool  
git checkout main  
git status # to confirm  
git merge test    
git status/log # to check  
git push  

### Other Useful Resources

#### Interacting with a remore Repo

https://help.github.com/articles/fetching-a-remote/  
https://stackoverflow.com/questions/17712468/what-is-the-difference-between-git-remote-update-git-fetch-and-git-pull  
