### Snap vs .deb

### 1. **Snap vs. `.deb` Packages**
   - **Snap**:
     - Snap packages are self-contained, making them easy to install and update. They automatically update in the background.
     - However, because they are isolated (sandboxed), they might not integrate as well with the system or other apps, as you noticed with Discord and VS Code.
   
   - **`.deb` Packages**:
     - `.deb` packages are the traditional way to install software on Debian-based systems like Ubuntu. They integrate better with the system and other applications.
     - However, you need to manually update them unless they’re from a repository that `apt` tracks.

### 2. **Mixing Snap and `.deb`**
   - It’s perfectly fine to mix Snap and `.deb` installations based on your needs. For apps that require close integration with other software (like Discord and VS Code), `.deb` packages are often better.
   - For apps where frequent updates or isolation are important (e.g., for security), Snap is a good choice.

### 3. **Checking for Updates**
   - **Snap**: 
     - Updates automatically, but you can manually check with:
       ```bash
       sudo snap refresh
       ```
   - **`.deb` Packages**: 
     - If the app is from a repository, you can update it with `sudo apt update` and `sudo apt upgrade`.
     - For manually downloaded `.deb` files (like Discord), periodically check the official website for new versions and install them as I described earlier.

### 4. **Managing Dependencies**
   - When dealing with `.deb` packages, sometimes dependencies need to be managed manually. The command `sudo apt --fix-broken install` is your friend when you encounter issues.

### 5. **Alternative Methods**
   - **AppImage**: Some applications also provide an AppImage, which is another form of portable application. AppImages don’t need installation, and you can run them directly. They’re self-contained like Snap but don’t auto-update.

[[Linux 101]]
[[Ubuntu Beginner Tut]]
#linux 