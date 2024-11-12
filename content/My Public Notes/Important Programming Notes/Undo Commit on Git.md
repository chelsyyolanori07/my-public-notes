### Undo the Last Commit
If you just made a commit and want to undo it (and keep the changes locally):

1. **Undo commit and keep changes in staging area:**
   ```bash
   git reset --soft HEAD~1
   ```
   This command will move the HEAD pointer of your current branch back one commit (`HEAD~1`), effectively undoing your last commit while keeping all the changes from that commit staged (ready to be committed again if needed).

2. **Undo commit and discard changes:**
   ```bash
   git reset --hard HEAD~1
   ```
   This command will move the HEAD pointer back one commit (`HEAD~1`) and discard all changes from the undone commit. **Use with caution**: this will permanently remove any changes introduced in the last commit.

### Undoing Older Commits
If you need to undo a commit that is not the most recent one, you can use `git log` to find the commit hash of the one you want to undo, and then reset to that commit:

1. **Find the commit hash:**
   ```bash
   git log
   ```
   Look for the commit you want to undo and copy its commit hash (the long string of characters).

2. **Reset to the commit before the one you want to undo:**
   ```bash
   git reset --hard <commit_hash>
   ```
   Replace `<commit_hash>` with the actual commit hash you copied from `git log`. This command will move the HEAD pointer and current branch pointer to the specified commit, effectively "undoing" all commits after that point.

### Undo and Preserve Changes
If you want to undo a commit but keep the changes introduced by that commit as unstaged changes in your working directory, you can use `git reset` with the `--mixed` option (which is the default behavior if no option is provided):

```bash
git reset HEAD~1
```

This command will undo the last commit, move the HEAD pointer back one commit, and keep the changes from that commit as unstaged changes in your working directory.

### Important Notes:
- **Be cautious:** Resetting commits will alter the history of your repository. If you've already pushed these commits to a remote repository, others may have based work on them. In such cases, it's generally better to use `git revert` to create a new commit that undoes the changes, rather than rewriting history with `git reset`.
  
- **Backup:** Before performing any operations that modify history, especially `git reset --hard`, make sure you have backups of any important changes or commits.

[[Git Important Notes]]
#git