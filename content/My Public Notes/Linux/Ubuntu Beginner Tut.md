- Hold shift before pressing restart button
- app center = to download app easily without using terminal
- sudo apt install neofetch = this is to install neofetch; neofetch displays information about your system in an aesthetic way
- to install app using this instead (the easier commands):
	- `snapd` is the background service that manages and runs Snap packages on your system. Snap packages are a type of software package that can be installed on various Linux distributions. They are self-contained and include all the dependencies and libraries they need to run, which simplifies the installation and maintenance of software.
	
		Here are some key points about `snapd` and Snap packages:
	
	1. Self-Contained: Snap packages bundle their dependencies, which helps to avoid conflicts with other software on your system.
	2. Automatic Updates: Snap packages can be updated automatically, ensuring you always have the latest version of your software.
	3. Security: Snaps run in a sandboxed environment, which enhances security by isolating the software from the rest of the system.
	4. Cross-Distribution: Snaps work across different Linux distributions without modification, providing a unified packaging format.
	
	To use Snap packages, you need to have `snapd` installed on your system. It usually comes pre-installed on newer versions of Ubuntu. If not, you can install it using:
	
	```bash
	sudo apt install snapd
	```
	
	Once `snapd` is installed, you can use the `snap` command to install, remove, and manage Snap packages. For example, to install Discord using Snap, you would use:
	
	```bash
	sudo snap install discord
	```
		
- Conclusion to remember better:

- **`sudo apt install <package>`**: Installs software from the Ubuntu repositories.
- **`sudo snap install <package>`**: Installs software using Snap packages.
- **`.deb packages**: Download and install with `dpkg -i`.

- Can see and custom it on setting
	- themes
	- dark mode
	- dock position
	- background

- system monitor / resources (memory) = the cpu information thingy
- top bar for wi-fi, volume, battery, shut down, etc
- second desktop 
- OS & software updates: software updater

[[Linux 101]]
#linux