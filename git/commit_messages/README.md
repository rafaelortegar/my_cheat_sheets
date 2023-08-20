To commit a message:
```bash
git commit -m "message to add"
```

To change the name of a commit after pushing to the repo:
```bash
# the 32 is the number of commits to go back
git rebase -i HEAD~32

# change from pick to reword
# save with ctrl+o and close with ctrl+x
# rename
git rebase --continue
git push -f
```
* [Cambiar un mensaje de confirmación](https://docs.github.com/es/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message)
* [git-rebase.markdown](https://gist.github.com/davidfeldi/c1cbdcbb9a8fa4bddbecdaab6a3c2357)
* [Writing a Good Git Commit Message](https://www.gitkraken.com/learn/git/best-practices/git-commit-message)
