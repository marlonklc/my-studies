### delete a remote branch
`git push <remote-name> --delete <branch-name>`

### sync forked project with your local project
first add forked project on remotes:
```
git remote add <remote-name-whatever> <url>
```
after that, fetch master branch of forked project:
```
git fetch <remote-name-whatever>
```
checkout your master branch:
```
git checkout master
```
so finally, merge you master branch with master branch of forked project:
```
git merge <remote-name-whatever>/master
```
### revert to specific commit and push (it must be used with caution)
```
git reset --hard <commit-hash>
git push -f origin <branch>
```
