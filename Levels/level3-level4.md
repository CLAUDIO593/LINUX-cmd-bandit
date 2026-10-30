## Bandit Level 3 --> Level 4
### 1. Objetivo del Nivel
La contraseña para el siguiente nivel está guardada en un archivo oculto del directorio `inhere`.
### 2. Comandos Utilizados
`ls`:Sirve para mostrar los archivos y carpetas que se encuentran en la carpeta actual donde estás posicionado.

`-l`: Muestra el formato de lista larga (long format). En lugar de solo ver los nombres, te da una tabla detallada con información clave de cada elemento:

- Los permisos de acceso (ej. `rwxr-xr-x`).

- El propietario y el grupo al que pertenece.

- El tamaño exacto en bytes.

- La fecha y hora de la última modificación.

`-a`: Muestra todos los elementos, incluidos los archivos ocultos (`all`). En Linux, los archivos y carpetas ocultos comienzan con un punto en su nombre (por ejemplo,` .document1 o .env`).

### 3. Como se resolvió este nivel
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct 25 13:37 .
drwxr-xr-x 3 root    root    4096 Oct 25 13:37 ..
-rw-r----- 1 bandit4 bandit3   33 Oct 25 13:37 ...Hiding-From-You
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You 
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```
