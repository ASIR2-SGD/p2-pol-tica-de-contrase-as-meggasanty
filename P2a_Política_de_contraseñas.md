# Política de contraseñas

## Contexto
Por defecto, la mayoría de sistemas operativos, vienene con una política de contraseña muy laxa, una contraseña segura presenta una barrera más al atacante, que en su intento de acceder al sistema, indudablemete dejará más rastro y en algunos casos a provocar el abandondo de ataque.

## Objetivos
* Entender el sistema de contraseñas del sistema operativo linux
* Entender el PAM (Plugable authentication Module)
* Instalar y configurar la libreria _pwquality_
* Comprobar y verificar que se ha llevado la práctica de forma correcta
* Documentar la práctica.

## Descripción práctica:
#### configurar 3 tipos distintos de plíticas de contraseñas.
* **Política débil**
* **Política media**
* **Política extrema**

## Inicio ejercicio.

#### Sistema de contraseñas
En linux, cuando el equipo requiere almacenar una contraseña la cadena de caracteres introducida por el usuario, se procesa para evitar que pueda ser robada. los procesos por los que pasa son los siquientes:

- Hashing: la cadena se transforma en en un código con una longitud de 512 bits. Este proceso no se puede revertir.
- Salting: el salting consiste en crear un prefijo aleatorizado para cada usuario, este prefijo se combina con el hash cada vez que se intenta iniciar sesión, y si la combinación de ambos (hash y salt) coincide con la almacenada en la base de datos del pc, entonces se permitirá el acceso. 
- Otros mecanismos de proteción son por ejemplo, las políticas de complejidad de contraseñas, que aseguran un mínimo para evitar que puedan ser vulneradas por fuerza bruta.
>[!NOTE] Ambos, el hash y el salt, se almacenan en el directorio /etc/shadow

#### Linux PAM
PAM es un conjunto de librerías que premiten al administrador configurar y modificar los métodos de autenticación de usuarios

PAM divide las tareas de autenticación en 4  grupos de gestión.
+ Módulo de cuentas
+ Módulo de autenticación
+ Módulo de contraseñas
+ Módulo de sesión

#### Instalación de pwQuality

1. Instalar la librería
``` sh
sudo apt-get install libpam-pwquality
```
2. instalamos también la siguiente, que nos permitirá utilizar herramientas adicionales
``` sh
sudo apt install libpwquality-tools
```

>[!TIP] Para comprobar que se ha instalado y activado, vamos a la carpeta /etc/pam.d/common-password. Si está activado, podremos observar una línea en la que se muestre el siguiente texto: pam_unix.so

3. Ahora modificaremos el archivo

| Política | Required Score | Longitud Mínima | Restricciones | Contraseña | pwScore | 
| :- | :- | :-  | :- | :- | :-: |
| No válida | <35 | - | - | kys3p2 | 23 |
| Débil | 35-50 | 6 |  minlen = 6 dcredit = -1 | 5Nyan? | 38 |
| Media | 50-80 | 8 | minlen = 8 dcredit = -1 ucredit = -1 lcredit = -1 | *HqkO0leR? | 68 |
| Extrema | >80 | 10 | minlen = 8 dcredit = -1 ucredit = -1 lcredit = -1 | Contra$eñaLarga1 | 100 |