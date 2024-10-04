
Steps/Issues when first installed

Had to download the executable from [here](https://github.com/yuk7/ArchWSL)

#### gpg ring issues

- I couldn't find the signature for one contributor, kept giving me issues.
	- Found solution [here](https://bbs.archlinux.org/viewtopic.php?id=282796)
	- the command is `pacman -Sy archlinux-keyring && pacman -Syu`

#### Installing [[paru]]

- had to install #git, #binutils for #makepkg, and #cmake first.
- Also had to do a [rustup](https://rustup.rs/) to install [[Rust]]
- Had to create a .conf to add --bottom-up as an option.
	- [ ] Add this to [[gnu stow]]

#### Pacman mirrorlist
- get reflector package
- run this command `sudo reflector --country US --age 12 --protocol https --sort rate --save /etc/pacman.d/mirrorlist`

#### Making new SSH Key
- [instructions from github](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
#### Add SSH to Github
- use the basic instructions

#### Programs to install
- add pacman.conf to settings
- bat
- lsd
- fzf
- ripgrep
- fd
- atuin
- zsh
	- fast-syntax-highlighting
	- zsh-autosuggestions
	- 

#### Adding Stow to migrate dotfiles
- install with [[paru]]

#### Adding my dotfiles config from git
- Had to add an ssh key to github for this system
- Added a profile using `git config --global user.email and user.name`

#### Other things to install


#### Making [[Nushell]] default

- I had to add #nu path to /etc/shells and then run `chsh -s /home/ivan/.cargo/bin/nu`


#### Locked out of user sudo
- ran wsl --user root
- `passwd <user>` updated then exited
- closed with `wsl --terminate Arch`
- reopened then it worked
- 


