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
* **Política débil (menos de 6 caracteres cualesquiera)**
* **Política media (mínimo 8 carateres [0-9], [A-Z])**
* **Política extrema (mínimo 12 caracteres [0-9], [A-Z], [a-z], [!"·$|@#~...])**

## Inicio.
En linux, cuando el equipo requiere almacenar una contraseña la cadena de caracteres introducida por el usuario, se procesa para evitar que pueda ser robada. los procesos por los que pasa son los siquientes
- Hashing: la cadena se transforma en en un código con una longitud de 512 bits. Este proceso no se puede revertir.
- Salting: 



| política | Restricciones | Contraseña 1 | pw score | Contraseña 2 | pw score | Contraseña 2 | pw score |
| :----- | :----- | :----- | :----: | :----- | :-----: | :----- | :-----: | :----- |
| Débil |  |  |  |  |  |  |  |  |
| Media |  |  |  |  |  |  |  |  |
| Extrema |  |  |  |  |  |  |  |  |