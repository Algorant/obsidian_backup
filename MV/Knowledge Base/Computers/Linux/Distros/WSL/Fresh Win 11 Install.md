#### Important Steps
- Enable HDR, set FPS to 120
- Enable virtualization in bios for WSL
- Get ArchWSL
- Use [ChrisTitusTech] tool to get all the apps
	- you saved a config on the homelab drives
- install a [[nerdfonts]]. In Windows Terminal it should be 
- Get Basic Powershell config, save to dotifles
- Set up SSH keys with 
- Remove Internet search from windows start menu search using [this](https://www.reddit.com/r/LinusTechTips/comments/1ahub6n/disabling_web_search_completely_fixes_windows/) link. Instructions are:
	- go to `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Search`
	- Make a new DWORD (32-bit) called: `BingSearchEnabled`
	- Ensure the value = 0
- Get [[Github]] working
	- add ssh key
	- set up [[Obsidian]] sync
	- set up [[Robochumba]] repo
		- install `axicli` with
			- `python -m pip install https://cdn.evilmadscientist.com/dl/ad/public/AxiDraw_API.zip`



#### Things to Save
- Axicli stuff
- Fonts
- Inkscape settings
- Documents (use gdrive to backup)
- Windows Terminal Config File
	- Fonts? Gogh? 
- 

#### New Installation
- Use instructions from this [video](https://www.youtube.com/watch?v=JUTdRZNqODY)
	- Uses specific instructions for creating iso in rufus + extra file found [here](https://github.com/memstechtips/UnattendedWinstall)
	- default pw is password
	- install programs later with CTT tool on desktop
	- Check out [Windhawk](https://windhawk.net/)

#### Programs to get with WinGet
- 7zip
- Deluge
	- [Dark theme installer here](https://github.com/delington/Deluge-theme-changer)
- 