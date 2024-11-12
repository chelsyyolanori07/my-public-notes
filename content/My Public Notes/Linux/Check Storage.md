### 1. Using the Disk Usage Analyzer (GUI)
1. Open the **Disk Usage Analyzer** app (search it in the applications menu).
2. It will scan the system and show a breakdown of storage usage.

### 2. Using the Terminal
Open a terminal (`Ctrl + Alt + T`) and run one of these commands:

- **Check disk space summary**:
   ```bash
   df -h
   ```
   - This displays available and used storage for each mounted file system in a human-readable format (`-h`).

- **Check folder sizes**:
   ```bash
   du -h --max-depth=1 /
   ```
   - This command shows the size of each top-level folder, helping identify large directories.

### Recommended (just because i am lazy hehehe)

Use this command to get a quick summary of the total remaining storage:

```bash
df -h --total | grep total
```

This will show a single line with total storage, used space, and available space for all drives combined :))

Example:
![[Screenshot from 2024-10-27 18-38-12 1.png]]

188 GB is the total amount of the storage left

[[Linux 101]]
[[Ubuntu Beginner Tut]]
#linux 