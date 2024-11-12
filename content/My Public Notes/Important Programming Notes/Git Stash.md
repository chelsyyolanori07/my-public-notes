### Scenario
You're working on a feature, but suddenly you need to switch to another task or branch without committing your current changes. You'll use Git stash to save your current work, switch tasks, and then come back to your original work.

### Step-by-Step Guide

1. **Open Your Project in VS Code**

   Ensure you have your project open in Visual Studio Code (VS Code) and that you have the terminal open in VS Code.

2. **Make Some Changes**

   Modify some files in your project. Let's say you change `file1.js` and `file2.js`.

3. **Check the Status of Your Changes**

   Open the terminal in VS Code and type:
   ```bash
   git status
   ```
   This will show you the modified files.

4. **Stash Your Changes**

   To save your current changes without committing them, use:
   ```bash
   git stash save "Work in progress on feature X"
   ```
   This command stashes your changes and provides a message to help you remember what the stash is for.

5. **Verify the Stash**

   Check the list of stashes to ensure your changes were saved:
   ```bash
   git stash list
   ```
   You should see your stash in the list.

6. **Switch to Another Branch**

   Now you can switch to another branch or work on a different task:
   ```bash
   git checkout another-branch
   ```
   If you need to create a new branch, use:
   ```bash
   git checkout -b new-branch-name
   ```

7. **Do Your Work on the Other Branch**

   Make any necessary changes and commits on the other branch.

8. **Switch Back to Your Original Branch**

   After finishing the other task, switch back to your original branch:
   ```bash
   git checkout original-branch
   ```

9. **Apply Your Stash**

   Apply your stashed changes back to your working directory:
   ```bash
   git stash pop
   ```
   This command applies the most recent stash and removes it from the stash list.

10. **Verify and Commit Your Changes**

   Check the status to ensure your changes are applied:
   ```bash
   git status
   ```
   Stage your changes:
   ```bash
   git add .
   ```
   Commit your changes:
   ```bash
   git commit -m "Completed feature X"
   ```

11. **Push Your Changes to GitHub**

   Push your changes to the remote repository:
   ```bash
   git push origin original-branch
   ```

### Summary of Commands

```bash
# Check status of changes
git status

# Stash your changes with a message
git stash save "Work in progress on feature X"

# List all stashes
git stash list

# Switch to another branch
git checkout another-branch

# (Do work on another branch, commit, etc.)

# Switch back to original branch
git checkout original-branch

# Apply the most recent stash and remove it from the stash list
git stash pop

# Verify changes
git status

# Stage changes
git add .

# Commit changes
git commit -m "Completed feature X"

# Push changes to GitHub
git push origin original-branch
```

### Visual Studio Code Integration

VS Code also provides a visual way to stash changes:

1. **Open Source Control View:**
   - Click on the Source Control icon in the Activity Bar on the side of the window.

2. **Stash Changes:**
   - Click on the `...` (More Actions) menu in the Source Control view.
   - Select `Stash > Stash Changes`.
   - Optionally provide a message for the stash.

3. **Apply Stash:**
   - Click on the `...` (More Actions) menu again.
   - Select `Stash > Apply Stash`.
   - Choose the stash you want to apply.

[[Git Important Notes]]
#git