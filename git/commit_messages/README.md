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
