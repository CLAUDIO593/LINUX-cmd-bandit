## Bandit Level 6 --> Level 7
### 1. Objetivo del Nivel
La contraseña para el siguiente nivel está guardada en algún lugar del servidor y cumple con todas las siguientes propiedades:

- pertenece al usuario bandit7 (owned by user bandit7)

- pertenece al grupo bandit6 (owned by group bandit6)

- 33 bytes de tamaño (33 bytes in size)"

### 2. Comandos Utilizados
En Linux, el sistema de permisos de archivos se basa en dos conceptos fundamentales: el usuario propietario (`User`) y el grupo (`Group`). Esta es la base de cómo el sistema operativo decide quién puede leer, escribir o ejecutar un archivo.

**¿Qué es el Usuario (Dueño u Owner)?**

En Linux, cada archivo o carpeta le pertenece estrictamente a una persona (un usuario).

- El usuario propietario es generalmente quien creó el archivo.

- Tiene el control principal sobre ese elemento y, por lo general, los permisos más altos sobre él.
- Nadie más debería poder leerlo a menos que el usuario se lo permita.

Decir que el archivo está "perteneciente al usuario bandit7" significa que, a nivel de propiedad principal, el archivo fue creado o es propiedad de la cuenta de usuario llamada bandit7

**¿Qué es el Grupo (Group)?**

Un grupo es una colección de usuarios que comparten ciertos accesos o permisos en común. En lugar de darle permisos archivo por archivo a 10 personas diferentes, el administrador mete a esas 10 personas en un mismo grupo (por ejemplo, el grupo desarrolladores) y le asigna permisos al grupo entero.Cualquier usuario que pertenezca a ese grupo heredará automáticamente esos permisos.

Ejemplo: Imagina una carpeta compartida en la oficina que dice "Equipo de Contabilidad". En ella trabajan Juan, María y Pedro. Los tres pertenecen al grupo Contabilidad. Si el archivo de la empresa se comparte con ese grupo, los tres podrán abrirlo, aunque no lo hayan escrito ellos mismos.

***ojo: En Linux, cada archivo tiene una sola etiqueta de Usuario y una sola etiqueta de Grupo. No se pueden sumar varios grupos principales a la vez para un mismo archivo.***

Para resolver el nivel 6 de Bandit (`bandit6 -> bandit7`), debes buscar en todo el servidor (a partir del directorio raíz /) un archivo que cumpla con los tres criterios solicitados:

`find /`: Inicia la búsqueda desde la raíz del sistema de archivos (/), es decir, en todo el servidor.

`-user bandit7`: Filtra los archivos cuyo dueño sea el usuario bandit7.

`-group bandit6`: Filtra los archivos que pertenezcan al grupo bandit6.

`-size 33c`: Filtra los archivos que pesen exactamente 33 bytes (la c representa bytes).

`2>/dev/null`: Redirige los mensajes de error (como "Permiso denegado" en carpetas a las que el usuario bandit6 no tiene acceso) al dispositivo nulo de Linux. Esto sirve para limpiar la pantalla y ver únicamente la ruta del archivo correcto.


### 3. Como se resolvió este nivel
```bash
bandit6@bandit:/$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null 
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:/$ cat /var/lib/dpkg/info/bandit7.password 
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
bandit6@bandit:/$ 
```