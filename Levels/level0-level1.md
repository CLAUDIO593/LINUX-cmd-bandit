## Bandit Level 0 --> Level 1
### 1. Objetivo del Nivel

La contraseña para el siguiente nivel está guardada en un archivo llamado `readme` que se encuentra en el directorio de inicio(`home`). Utiliza esta contraseña para iniciar sesión en `bandit1` mediante SSH. Cada vez que encuentres la contraseña de un nivel, utiliza SSH (en el puerto 2220) para iniciar sesión en ese nivel y continuar el juego.

### 2. Comandos Utilizados
- `ls` (List)<br>

Lista los archivos y carpetas que se encuentran dentro del directorio actual en el que estás posicionado.

```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ 
```

- `cd` (Change Directory)

Permite navegar y cambiar de una carpeta a otra dentro del sistema de archivos.
- `cat` (Concatenate)

Lee, muestra en pantalla o combina el contenido de uno o varios archivos de texto sin necesidad de abrir un editor complejo.

```bash
bandit0@bandit:~$ cat readme 
The password you are looking for is: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
bandit0@bandit:~$ 
```
**la contraseña se remplazo con xxxxxx para ocultarla**

- `file` 

Analiza un archivo e identifica su tipo real (por ejemplo, si es un script de texto, una imagen PNG, un binario ejecutable o un documento comprimido), sin importar la extensión que tenga en su nombre

```bash
bandit0@bandit:~$ file readme 
readme: ASCII text
bandit0@bandit:~$ 
```

- `du` (Disk Usage)

Muestra el espacio en disco que están ocupando los archivos y directorios. Es muy útil para identificar qué carpetas están consumiendo más almacenamiento.

```bash
bandit0@bandit:~$ du readme 
4	readme
bandit0@bandit:~$ 

bandit0@bandit:~$ du -h readme 
4.0K	readme
bandit0@bandit:~$
```
significa que el archivo llamado `readme` ocupa `4` kilobytes de espacio en el sistema.

usa `-h `para mostrar un resultado claro como `4K` (kilobytes)

- `find`

Busca archivos y directorios en todo el sistema de archivos utilizando diferentes criterios de filtrado, como nombre, tamaño, fecha de modificación o permisos.

```bash
bandit0@bandit:~$ find readme
readme
bandit0@bandit:~$ 
```
### 3. Como se resolvió este nivel
usando el comando cat para que muestre el contenido del archivo readme se obtiene la contrasena para este nivel
```bash
bandit0@bandit:~$ cat readme 
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: xxxxxxxxxxxxxxxxxxxxx

bandit0@bandit:~$ 
```
### 4. Como entrar al level1
``` bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
Pasword: # el que acabamos de encontrar en el paso 3.
```