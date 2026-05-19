# ¡Configuramos Waybar para Hyprland!

[ver el video](https://www.youtube.com/watch?v=GG_UzS3EyO4)

## descripción:

En este video, continuamos configurando hyprland desde cero, enfocándonos en solucionar un problema con los íconos de Waybar. Aprenderás a ajustar tu waybar config para que todo funcione correctamente en tu arch linux hyprland y mejorar tu experiencia con este tiling window manager. Este linux tutorial te guiará paso a paso para que tu hyprland setup esté impecable.

### Links mencionados

- [repo oficial](https://github.com/alexays/waybar)
- [wiki de hyprland](https://wiki.hypr.land/Useful-Utiliti...)
- [catpuccin para waybar](https://github.com/catppuccin/waybar)
- [archivos de configuración de catpuccin para waybar](https://github.com/rubyowo/dotfiles/tree/f925cf8e3461420a21b6dc8b8ad1190107b0cc56/config/waybar)
- [el css de mocca que usé](https://github.com/catppuccin/waybar/releases/tag/v1.1)

### comandos usados

Crear el directorio de configuración:
```bash
mkdir ~/.config/waybar
```

Navegar al directorio:
```bash
cd ~/.config/waybar
```

Copiar la configuración por defecto:
```bash
cp -r /etc/xdg/waybar .
```

Instalar el paquete necesario para los iconos:
```bash
sudo pacman -S otf-font-awesome
```

Gestionar archivos de estilo (CSS) y respaldos:

Renombrar archivo original para respaldo:
```bash
mv style.css style.css.bkp
```

Crear nuevo archivo de estilo:
```bash
vim style.css
```

Reiniciar Waybar:
Aunque no siempre se muestra el comando exacto, el autor menciona que debes matar las instancias previas (usualmente con `killall waybar`) y volver a ejecutar el binario simplemente escribiendo `waybar` en la terminal.
```bash
killall waybar
waybar
```

-----------------------