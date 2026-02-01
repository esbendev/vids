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

## Script para automatizar las pruebas
```bash
#!/bin/bash

# primero hago free -h y guardo
# la cantidad de memoria usada en una variable
MEMORIA_USADA=$(free -h | grep Mem | awk '{print $3}')
sleep 5
# luego sumo %CPU y %MEM de los 10 procesos que más memoria usan
read SUMA_CPU SUMA_MEM < <(ps aux --sort=-%mem | head -n 11 | awk 'NR>1 {sum_cpu += $3; sum_mem += $4} END {print sum_cpu, sum_mem}')
sleep 5
# luego corro sysbench cpu --threads=4 run y 
# guardo el valor de "events per second:"
EVENTOS_POR_SEGUNDO=$(sysbench cpu --threads=4 run | grep "events per second:" | awk '{print $4}')
sleep 5
# luego corro sysbench memory run y 
# guardo el valor de "total operations" que está
# en parentesis con decimales
TOTAL_OPERACIONES_POR_SEGUNDO=$(sysbench memory run | grep "Total operations:" | awk -F'[()]' '{print $2}' | awk '{print $1}')
sleep 5

# luego los demonios haciendo systemctl --user list-units --type=service --state=running | wc -l 
DEMONIOS_CORRIENDO=$(systemctl --user list-units --type=service --state=running | wc -l)

# Opcional: imprimir los resultados
echo "Memoria usada: $MEMORIA_USADA"
echo "Suma de %CPU: $SUMA_CPU"
echo "Suma de %MEM: $SUMA_MEM"
echo "Eventos por segundo: $EVENTOS_POR_SEGUNDO"
echo "Total operaciones: $TOTAL_OPERACIONES_POR_SEGUNDO"
echo "Demonios corriendo: $DEMONIOS_CORRIENDO"
```