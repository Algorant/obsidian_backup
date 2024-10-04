
In order to bootstrap faster (in theory!) and not maintain deps so much, trying to use Lazyvim as default and modify my config off of it.

#### Todos
- [ ] whichkey mods
	- [x] a for avante
	- [x] put all harpoons in their own thing, h
	- [ ] figure out save thing
	- [ ] put plugins in p, add mason, lazy, and lazy extras
	- [ ] use / or \\ for terminals
- [ ] use that context line thing instead of bufferline, or just add it for now
- [ ] get [[whichkey]] in [[telescope]] 
- [ ] Figure out how to get cmdline in [[noice]] to work nicely. I have it in the right position, but the popupmenu does not work as intended, it stays at the top
- [ ] figure out neoscroll issue


#### Notes
- For getting the rust extras working
	- install rust-analyzer separately, NOT with [[mason]]
	- `rustup component add rust-analyzer`
	- source from [reddit](https://www.reddit.com/r/neovim/comments/1cpruok/rust_not_working_in_lazyvim/)
- s in normal mode seems to enable [[flash]]
- , should remap to fb (telescope context for buffers)
- Capital H, L goes between buffers

#### New Stuff
- Leader u for ui stuff
	- disable inlay hints, etc
- 
