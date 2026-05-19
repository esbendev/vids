# !La terminal más útil! (kitty con starship, eza, fzf, bat)

[ver el video](https://www.youtube.com/watch?v=xDlWKhbzIe0)

### Links mencionados

- [página de starship](https://starship.rs)
- [guía de starship](https://starship.rs/guide/)
- [temas (themes) de starship](https://starship.rs/presets/)
- [repo de eza](https://github.com/eza-community/eza)
- [repo de fzf](https://github.com/junegunn/fzf)


### comandos usados

Para cambiar el tema en kitty
```bash
kitten themes
```

Para cambiar la fuente (font)
```bash
kitten choose-font
```

instalar starship
```bash
pacman -S starship

# luego agregamos esto a nuestro ~/.bashrc
eval "$(starship init bash)"
```

Para cambiar el tema de starship
```bash
#para catpuccin usé este, pero fijense en el link de temas que puse arriba y elijan el que les gusta a uds!!
starship preset catppuccin-powerline -o ~/.config/starship.toml
```

Para instalar eza
```bash
sudo pacman -S eza

# agregamos la configuración a nuestro ~/.bashrc
alias ls='eza'
alias ll='eza -lag --icons --git'
alias lt='eza --tree --level=2'
alias la='eza -a'

```

Para instalar fzf
```bash
sudo pacman -S fzf

# agregamos la configuración a nuestro ~/.bashrc
eval "$(fzf --bash)"
```

Para instalar bat
```bash
sudo pacman -S bat
```

si quieren reemplazar cat con bat
```bash
# agregar a nuestro ~/.bashrc
alias cat='bat'
```

Mi configuración de fzf
```bash
# Preview files with bat and folders with eza when pressing Ctrl+T
export FZF_CTRL_T_OPTS="--preview 'if [ -d {} ]; then eza --tree --color=always --icons {}; else bat --style=numbers --color=always --line-range :500 {}; fi'"

# Preview directory trees with eza when pressing Alt+C
export FZF_ALT_C_OPTS="--preview 'eza --tree --color=always --icons {} | head -200'"
```