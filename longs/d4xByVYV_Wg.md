# ¡Configuramos Hyprpaper en Hyprland!

[ver el video](https://www.youtube.com/watch?v=d4xByVYV_Wg)

### Links mencionados

- [wiki de hyprland](https://wiki.hypr.land/Hypr-Ecosystem/hyprpaper/)
- [repo de hyprpaper](https://github.com/hyprwm/hyprpaper)
- [fotos de NASA](https://www.nasa.gov/gallery/lunar-flyby/)
### comandos usados

Para instalar hyprpaper
```bash
sudo pacman -S hyprpaper
```

para ver el id de tus monitores
```bash
hyprctl monitors
# o con awk para obtener solo los ids:
hyprctl monitors | awk '/monitor/ {print $2}'
```

para listar los archivos nuevos de configuración
```bash
ls ~/.config/hypr/conf/*.conf | awk '{print "source = " $1}' > ~/.config/hypr/hyprland.conf
```

en vim usé:
```vim
:m [número de linea donde quiero que queda la linea actual]

ejemplo:

:m 0
```

-----------------------