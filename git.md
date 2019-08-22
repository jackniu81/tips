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
