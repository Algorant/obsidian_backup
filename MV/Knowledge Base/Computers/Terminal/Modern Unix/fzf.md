#### Working Code for fzf file manager so far

```
find \( -type d -name '.git' -o -name '.cache' -o -name '.local' \) -prune -o -type d -print | \
fzf \
--bind "enter:execute(nvim {})" \
--bind "alt-o:execute(cd {})" \
--bind "del:execute(rm -ri {})" \
--bind "?:toggle-preview" \
--bind "ctrl-d:change-prompt(Dirs > )" \
--bind "ctrl-d:+reload(find -type d)" \
--bind "ctrl-d:+change-preview(tree -aC {} | head -n 10)" \
--bind "ctrl-d:+toggle-preview" \
--bind "ctrl-f:change-prompt(Files > )" \
--bind "ctrl-f:+reload(find -type f)" \
--bind "ctrl-f:+change-preview(bat -n --color=always {})" \
--bind "ctrl-f:+toggle-preview" \
--header "CTRL+R to delete | ENTER to run nvim | DEL to delete | CTRL-D to display directories | CTRL-F to display files" \
--height 60% --border --preview-window hidden --preview "tree -aC {}" --prompt "Dirs > "
```

Works great, except its just in terminal, not through [[zsh]], and doesn't cd, and doesn't account for images

Add leading backslashes to make other variables and stuff work!!