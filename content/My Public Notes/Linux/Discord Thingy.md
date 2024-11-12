### Case 1 (Not recommended)

Since your Discord app is from the official `.deb` package, you can update it without needing to switch to the Snap version. Here’s how to update your Discord to resolve the "update required" message:

### Update Discord from the Official `.deb` Package

1. **Remove the Old Version:**
   First, you should remove the existing version of Discord to avoid conflicts:
   ```bash
   sudo apt remove discord
   ```

2. **Download the Latest Version:**
   Visit the [Discord download page](https://discord.com/download) and download the `.deb` package for Linux.

   Or, download it directly using:
   ```bash
   wget "https://discord.com/api/download?platform=linux&format=deb" -O discord.deb
   ```

3. **Install the New Version:**
   Install the downloaded `.deb` package with the following command:
   ```bash
   sudo dpkg -i discord.deb
   ```

4. **Fix Any Dependency Issues:**
   If the installation shows dependency errors, run:
   ```bash
   sudo apt --fix-broken install
   ```

5. **Reopen Discord:**
   Launch Discord as usual. It should now be updated, and your VS Code activity should still be visible.

This method updates your Discord app without changing its source or affecting its integration with other apps like VS Code.

### Case 2 (Recommended)

To update Discord without uninstalling it first, you can directly install the new `.deb` package over the existing one. Here’s how:

### Steps to Update Discord Without Uninstalling

1. **Download the Latest Discord `.deb` Package:**
   You can download it from the official [Discord website](https://discord.com/download) or use the Terminal:
   ```bash
   wget "https://discord.com/api/download?platform=linux&format=deb" -O discord.deb
   ```

2. **Install the New Package:**
   After downloading the `.deb` file, run the following command to install it:
   ```bash
   sudo dpkg -i discord.deb
   ```
   This command will update the existing Discord installation without uninstalling it.

3. **Fix Dependencies (if needed):**
   If you encounter any dependency issues during installation, you can resolve them by running:
   ```bash
   sudo apt --fix-broken install
   ```

### Summary

- No need to uninstall Discord first.
- Simply downloading the new `.deb` file and installing it with `dpkg -i` will update Discord while keeping the settings and data intact.

[[Ubuntu Beginner Tut]]
#linux 