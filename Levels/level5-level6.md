## Bandit Level 5 --> Level 6
### 1. Objetivo del Nivel
La contraseña para el siguiente nivel está guardada en un archivo en algún lugar dentro del directorio `inhere` y cumple con todas las siguientes propiedades:

* legible por humanos (human-readable)

* 1033 bytes de tamaño (1033 bytes in size)

* no ejecutable (not executable)"

### 2. Comandos Utilizados
`find` .: Busca a partir del directorio actual y en todas sus subcarpetas.

`-type f`: Le indica que busque únicamente archivos (no carpetas).

`-size 1033c`: Filtra exactamente los archivos que pesen 1033 bytes (la "c" significa caracteres/bytes).

`! -executable`: El signo de exclamación ! niega la condición, por lo que le ordena que no sea un archivo ejecutable.

### 3. Como se resolvió este nivel
```bash
bandit5@bandit:~$ 
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls 
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find -type f -size 1033c ! -executable # encuentra el archivo
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2 # Abre el archivo
xxxxxxxxxxxxxxxxxx
```
