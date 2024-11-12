 ### Basic Snap Commands
- Check snap version 
	- `snap version` 
	- Display the version of snapd and other related information
- Install a snap package
	- `sudo snap install <package name>`
	- Replace the package name with the name of the package you want to install
- Remove a snap package
	- `sudo snap remove <package name>`
	- Replace the package name with the name of the package you want to remove
- List installed snap packages
	- `snap list`
	- Lists all installed snap package on your system
- Search for snap packages
	- `snap find <search term>`
	- Searches for snap packages matching
- Update snap packages
	- `sudo snap refresh`
	- Updates all installed snap packages to their latest version
- View snap package details
	- `snap info <package name>`
	- Displays detailed information about the package name you write
- List available snap version
	- `snap list --all`
	- Lists all versions of installed snap packages including those are no longer active
- Check for available snap update
	- `snap rfresh --list`
	- Lists available updates for snap packages
- Get logs for a snap service
	- `journalctl -u snap.<package name>.<service name>`
	- View logs for a specific snap service. Replace the package name and the service name 

[[Linux 101]]
[[Ubuntu Beginner Tut]]
#linux