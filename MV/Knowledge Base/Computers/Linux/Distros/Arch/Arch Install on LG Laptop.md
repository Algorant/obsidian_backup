
#### Steps Taken
- Get #arch torrent iso
- Install from #windows pc using #rufus
- use `archinstall` command when installing
- used defaults from video by [Mental Outlaw](https://www.youtube.com/watch?v=G-mLyrHonvU&t=201s)
- installed #paru
- 

#### Issues

- Touchpad doesn't work
	- Used recommended arch backup and added it to [[gnu stow]] dotfiles under #xorg
- Volume is at 0 by default.
	- Was able to connect a different widget in [[qtile]] that responded to this instead. I think it has to do with how pipewire is now what is connecting.
- [[Starship]] prompt broke
	- this was [[Nushell]]s fault, not mine, they happened to update at same time. But I was able to fix this as well
	- Fonts didn't work until I installed a #nerdfont in [[kitty]] and then added both symbol and emoji support:
		- `paru ttf-joypixels`
		- `paru ttf-nerd-fonts-symbols`
- Added transparency to dropdown menu
- 