## Bandit Level 4 --> Level 5
### 1. Objetivo del Nivel
La contraseña para el siguiente nivel está guardada en el único archivo legible por humanos que hay en el directorio `inhere`. 

Consejo: si tu terminal no funciona bien, prueba con el comando `reset`.
### 2. Comandos Utilizados

`file` sirve para determinar su tipo real (por ejemplo, si es un script de texto, una imagen PNG, un binario ejecutable o un documento comprimido), sin importar la extensión que tenga en su nombre.

`*` es un carácter comodín en la terminal que representa "cualquier cadena de caracteres" (o "todo lo que haya").

- Si escribes solo `*`, la terminal expande esa instrucción para referirse a todos los archivos y carpetas que existen en esa carpeta.

- Si escribes `*.txt`, le estás diciendo a la terminal "todos los archivos que terminen en .txt".

¿Qué hace la co
### 3. Como se resolvió este nivel
```bash
bandit4@bandit:~$ ls # lista lo que hay en este directorio
inhere
bandit4@bandit:~$ cd inhere/ # ingresa al directorio inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./* # determina que tipo de archivo es cada uno. -file07 tiene texto plano, este archivo contiene la contraseña
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx # la contraseña se remplazo con 
bandit4@bandit:~/inhere$ 
```