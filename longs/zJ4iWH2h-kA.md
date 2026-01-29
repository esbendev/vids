# ¿Cuál usa menos RAM GNOME, KDE o Cosmic?

[ver el video](https://www.youtube.com/watch?v=zJ4iWH2h-kA)

## descripción
En este video, comparo el rendimiento de diferentes escritorios: GNOME, KDE Plasma y Cosmic, buscando el sistema operativo perfecto para 2026. Muestro datos de uso de RAM y CPU, así como los procesos más pesados, para determinar cuál es el más eficiente en mi arch linux base. Esta es una guía esencial para quienes buscan optimizar su desktop en linux.

## comandos usados

### para probar el uso de RAM y CPU
```bash
free -h         
```

```bash 
htop   
```

```bash 
btop
```

```bash 
ps aux --sort=-%mem | head -10  
```

### lo de firefox
```bash
firefox --new-instance (4 paginas) &
# la & al final es para que se abra en segundo plano
# así podes usar la misma terminal para otras cosas
```

### demonios
```bash
systemctl --user list-units --type=service --state=running | wc -l 
```

## para instalar y desinstalar escritorios
### CINNAMON
```bash
sudo pacman -S cinnamon nemo-fileroller
```

```bash 
sudo pacman -Rns cinnamon nemo-fileroller
sudo pacman -Rns $(pacman -Qdtq)
```

### BUDGIE
```bash 
sudo pacman -S budgie
```

```bash 
sudo pacman -Rns budgie
sudo pacman -Rns $(pacman -Qdtq)
```

### DEEPIN
```bash 
sudo pacman -S deepin deepin-extra
```

```bash 
sudo pacman -Rns deepin deepin-extra
sudo pacman -Rns $(pacman -Qdtq)
```