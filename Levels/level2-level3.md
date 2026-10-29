## Bandit Level 2 --> Level 3
### 1. Objetivo del Nivel
La contraseña para el siguiente nivel está guardada en un archivo llamado  `--spaces in this filename--`, ubicado en el directorio de home.
### 2. Comandos Utilizados
En Linux, si intentas abrir un archivo cuyo nombre tiene espacios. La terminal se confundirá y creerá que son dos archivos distintos.
Para solucionar esto y que la terminal entienda que el espacio forma parte del nombre, tienes tres métodos principales:

- **Usar comillas (`""`)**

Encierras todo el nombre del archivo entre comillas dobles (" ") o comillas simples (' '). La terminal interpretará todo lo que está adentro como un solo bloque:

```bash
cat "documento uno"
```
- **Usar la barra invertida o escape (`\`)**

Puedes colocar una barra invertida justo antes de cada espacio. Esto le indica a la terminal que ignore temporalmente el significado especial del espacio:
```bash
cat documento\ uno
```
- **El autocompletado con la tecla Tab**
Escribe solo las primeras letras del archivo (por ejemplo, `cat doc`) y presiona la tecla Tab en tu teclado. Linux completará automáticamente el nombre por ti y le añadirá las barras invertidas necesarias:

### 3. Como se resolvió este nivel
```bash
bandit2@bandit:~$ ls
--spaces in this filename--
# método 1 usando comillas simples
bandit2@bandit:~$ cat ./'--spaces in this filename--'
# método 2 usando barra invertida
bandit2@bandit:~$ cat ./--spaces\ in\ this\ filename--
```
