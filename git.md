# Git Tips
## Get code from other branch (e.g. master)

git pull origin master

## Clean .get folder to make it smaller

git gc --prune=now

## Shrink .git folder size
git gc --prune=now

## git commit
### empty commit
git commit --allow-empty -m "Merge with conflict"

## git config
### Set global proxy
git config --global http.proxy http://proxyUsername:proxyPassword@proxy.server.com:port

## Force to restore to a branch
`git reset --hard origin/master`

## (un)ignore files for submit
```
git update-index --assume-unchanged <file>
git update-index --no-assume-unchanged <file>

// e.g. 
git update-index --assume-unchanged config.json
git update-index --no-assume-unchanged config.json

// unignore all files
git update-index --really-refresh
```



## Merge but need to discard the changes
git commit --allow-empty -m "Merge with conflict"


## tag
```
git tag "your_tag_name"
git push origin --tags
```

## archive source to zip
git archive -o source.zip HEAD

## undo last PUSH
```
git reset --hard HEAD~1
git push --force
```
Rollback to certain commit
```
git reset --hard 543acea
git push --force
```
## clean repository

### Git Clean
Step 1 is to show what will be deleted by using the -n option:

git clean -n
Clean Step - beware: this will delete files:

git clean -f
	* To remove directories, run git clean -f -d or git clean -fd
	* To remove ignored files, run git clean -f -X or git clean -fX
	* To remove ignored and non-ignored files, run git clean -f -x or git clean -fx



### Git Clean - Remove un-tracked/ignored folders and files
git clean -fxd
