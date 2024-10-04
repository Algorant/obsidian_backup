
## Todo
- [x] make scratchpad / dropdown terminal using hyprctl? 
- [ ] [[swaylock]] test
	- [x] configure [[swaylock]] and also get [[swayidle]] and perhaps get the fancy git stuff
	- [ ] customize the circle thing
	- [ ] customize the background or fix screenshot timing
- [ ] volume and brightness control shortcuts
	- [ ] [[rofi]]? [[eww]]?
- [ ] [[ncspot]] in [[waybar]] ?
- [ ] notifications with [[eww]]
	- [ ] one for screenshots taken
- [ ] add more aliases
	- [ ] git ones
	- [ ] config ones
- [ ] shorten configs, remove comments and unused

-----

### Programs 
- [[Obsidian]]
- [[Firefox]]
	- uses gtk theming using [[nwg-look]]
	- also consider modifying with [Firefox-Mod-Blur](https://github.com/datguypiko/Firefox-Mod-Blur)
- [[thunar]]
	- needs a package called [[tumbler]] to view thumbnails
	- uses gtk theming using [[nwg-look]]
- [[Slack]]
	- has ability to zoom in with settings
- [[OBS]]
- [[Steam]]
	- needed to install libraries for vulkan to work:
		- Got them from Lutris repo [here](https://github.com/lutris/docs/blob/master/InstallingDrivers.md)
		- 
---
### Command Line Tools
- [[Starship]]
- [[fastfetch]]
- [[ranger]]
	- needs [[PIL]] to show images
- Core
	- [[less]]
	- [[mandoc]]
	- [[zsh]]
	- [[tree]]
- [[Modern Unix]]
	- [[bat]] 
	- [[lsd]]
	- [[duf]]
- [[nu]]
- [[atuin]]
- [[auto-cpufreq]]
- [[fzf]]
- [[ripgrep]]
- [[bottom]]

---

### Sound / Networking
- pipewire, wireplumber, pipewire-audio, pipewire-pulse
- network manager, network manager applet
- blueman
- Bluetooth Troubleshooting
	- I had to do
		- `systemctl enable/start bluetooth`
- Networking Troubleshooting
	- After installing nm-applet and network manager, I had to do
		- `sudo systemctl restart NetworkManager.service`
	- I also used iwd/iwctl to initially connect to internet during the #arch install
	- so, I basically had to convert NetworkManager to use iwd as a backend, then disable iwd and reboot:
	- Instructions for adding it are [here](https://wiki.archlinux.org/title/NetworkManager#Using_iwd_as_the_Wi-Fi_backend) on the #arch #wiki
	- There are some more instructions [here](https://www.reddit.com/r/archlinux/comments/11y1qik/switching_from_iwd_to_networkmanager/) as well as a reddit discussion about it


---

### Hyprland / WM / Wayland specific
- [[waybar]]
- [[wlogout]], nice logout screen in wayland
- [[swww]] and [[waypaper]] 
	- For backgrounds and transitions
- [[swaylock]] lockscreen 
- [[grimblast]] screenshot utility (uses grim + slurp)
- [[pywal]] not being used yet, but can automate colorschemes
- [[wl-clipboard]] #wayland clipboard
- [[pyprland]] for scratchpads

---

### Fonts (NerdFonts)
- ttf-font-awesome, ttf-jetbrains-mono-nerd, noto-fonts-emoji, noto-fonts

---

### Appearance / Themes
- [[nwg-look]]
	- there is also [[lxappearance]], but firefox only changed with [[nwg-look]]
- [[qt5-ct]]
	- Note: need to edit etc/config to add 
#### Gruvbox stuff
- GTK
	- gruvbox-dark-gtk 
	-  gtk-engine-murrine
	-  bettergruvbox-gtk-theme 
	-  gruvbox-dark-icons-gtk 

---
### Languages
- [[Rust]] (rustup)
- [[Python]]
- [[node]] / [[npm]]