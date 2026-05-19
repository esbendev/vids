# Las 5 Mejores Distros Linux para Principiantes en 2026

[ver el video](https://www.youtube.com/watch?v=0HDOG6iTlsM)

## descripción:

En este video, te mostramos cómo instalar y configurar "hyprland" desde cero en "arch linux hyprland". Usaremos "kitty terminal" como nuestro "terminal emulator" para este "linux tutorial". Descubre el proceso paso a paso para tener tu sistema operativo listo y funcionando.

### Links mencionados
[Hyprland](https://hyprland.org/)
[wiki de hyprland](https://wiki.hypr.land/)
[Guía](https://wiki.hypr.land/Getting-Started/Master-Tutorial)
[para los fonts](https://nerdfonts.com/)

### comandos usados

instalamos hyprland y kitty
```bash
sudo pacman -S hyprland kitty
```

entramos a hyprland
```bash
start-hyprland
```

el archivo de configuración de hyprland se encuentra en
```bash
~/.config/hypr/hyprland.conf
```

#### cosas que instalé
```bash
sudo pacman -S dolphin hyprlauncher
```

```bash
sudo pacman -S waybar hyprpaper firefox
```

```bash
sudo pacman -S swaync
```

```bash
sudo pacman -S pipewire wireplumber
```

```bash
sudo pacman -S xdg-desktop-portal
```

```bash
sudo pacman -S hyprpolkitagent
```

```bash
sudo pacman -S qt5-wayland qt6-wayland
```

#### para los fonts
```bash
mkdir -p ~/.local/share/fonts
```

```bash
fc-cache -fv
```

```bash
fc-list | grep "Nerd"
```

en kitty, para elegir el font
```bash
kitten choose-fonts
```
-----------------------