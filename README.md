# Redireccionamiento

Enunciado:
Genera un archivo llamado informe.txt que contenga:
* La fecha del sistema formateada (dia, mes y año).
* El espacio en disco (df -h).
* Memoria libre del sistema (free -h).
* Usuarios conectados.

**Código usado**
```bash
#!/bin/bash
RED='\033[0;31m' #Para dar estilo a nuestro output primero tenemos que definir en una variable el color.
BLUE='\033[0;94m'
LBLUE='\033[1;34m'
YELLOW='\033[0;33m'
NC='\033[0m' #NC para No Color, porque si no se pondría todo el output de ese color.
echo ${BLUE}La fecha de hoy es:${NC} $(date +"%d-%m-%Y")
echo ${RED}===================================================================${NC}
echo ${BLUE}El espacio en disco libre es:${NC}
df -h
echo ${YELLOW}===================================================================${NC}
echo ${BLUE}Memoria RAM usada, total y libre:${NC}
free -h
echo ${RED}===================================================================${NC}
echo ${BLUE}Usuarios conectados:${NC}
who
echo ${LBLUE}Script realizado por: Jesús González Aragón${NC}
```
> Hay que subir imagen de que el script ha sido ejecutado con éxito.
![script](prueba_script.png)

Explicación un poco más profunda del color en el script:

Se usa un método llamado ANSI Escape. 
* Con el '\033 se indica en octal el caracter ESC, lo cual le dice al script que lo que sigue es una secuencia ANSI, que es una combinación de caracteres usada en terminales y consolas para controlar cosas como el formateado de texto.

En "\033[0;31m" ya sabemos que \033 significa la tecla ESC.

* El "[" es un separador.

* El "0" significa que reinicie todos los estilos si es que hubiera alguno y lo devuelva a su estado predeterminado (ninguno).

* El ";" es otro separador.
  
* El "31" indica el color, en este caso, rojo.

* Y la "m" significa que estamos definiendo el estilo.


Pequeña tabla de algunos colores:
Color | Código
|-----|-------|
Negro | 0;30
Rojo | 0;31
Verde | 0;32
Naranja | 0;33
Azul | 0;34
Morado | 0;35
Cian | 0;36
Gris claro | 0;37
