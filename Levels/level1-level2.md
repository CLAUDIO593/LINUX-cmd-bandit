## Bandit Level 1 --> Level 2
### 1. Objetivo del Nivel
La contraseña para el siguiente nivel está guardada en un archivo llamado `—`, que se encuentra en el directorio de inicio.
### 2. Comandos Utilizados
En linux el `-` (guion) se utiliza para indicar una bandera por ejemplo (`ls -l`) por lo que al querer usar comando `cat` `nombre_del_archivo` en este caso  (`-`) el comando piensa:

- Que estas intentando pasar una opción de bandera(`flag`)
- O, en el caso de comandos como cat o grep, un guion solitario le indica a la terminal que debe leer desde la entrada estándar (stdin), por lo que el programa se quedará "congelado" esperando a que escribas algo con el teclado.


### 3. Como se resolvió este nivel
Para evitar que la terminal confunda el nombre de un archivo con una opción de comando, existe una solución:

- **Usar la ruta relativa (`./`)**

Una ruta relativa es una dirección que le indica a la terminal o al sistema operativo cómo llegar a un archivo o carpeta partiendo desde el lugar exacto en el que te encuentras ubicado en ese momento (tu directorio de trabajo actual).

Ejemplo práctico: Si estás ubicado dentro de la carpeta `/home/bandit1/` y ahí dentro hay un archivo llamado `readme.txt`, su ruta relativa es simplemente `readme.txt` (o `./readme.txt`, donde el `./` significa explícitamente "aquí mismo, en este directorio").

```bash
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
XXXXXXXXXXXXXXXXXXXXXXX
bandit1@bandit:~$ 
```

---

**¿Cuántos tipos de rutas existen?**

los sistemas operativos (como Linux, macOS y Windows), existen dos tipos principales de rutas para ubicar archivos y directorios:

- **Ruta Absoluta (Absolute Path)**

Es la dirección completa e invariable de un archivo o carpeta, que comienza siempre desde la raíz absoluta del disco duro. No importa en qué rincón del sistema te encuentres parado; si usas una ruta absoluta, el sistema llegará al archivo sin dudar.

En Linux y macOS: Siempre empiezan con una barra diagonal inicial `/` (que representa la raíz o root del sistema).

Ejemplo: /home/bandit1/settings/config.json


**Ruta Relativa (Relative Path)**

Es la dirección basada enteramente en tu posición actual. Su valor cambia dependiendo de dónde esté posicionada tu terminal en ese instante.

Utiliza atajos estándar para navegar por el árbol de directorios:

`./ ` o el nombre directo: Representa el directorio actual.

`../` Representa el directorio superior (subir un nivel hacia la carpeta "padre").

`~/` El símbolo ~ (virgulilla o tilde) representa el directorio personal (Home directory) del usuario que tiene la sesión abierta en la terminal.
Si tu usuario es `bandit1`, la terminal interpreta `~/` como la ruta absoluta `/home/bandit1/`. Si tu usuario es `root`, la terminal la interpreta como `/root/`