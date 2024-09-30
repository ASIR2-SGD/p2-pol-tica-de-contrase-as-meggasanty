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
(https://es.eitca.org/cybersecurity/eitc-is-lsa-linux-system-administration/basic-linux-sysadmin-tasks/user-account-management/examination-review-user-account-management/how-are-passwords-stored-and-managed-in-linux/#:~:text=Cuando%20un%20usuario%20crea%20una,para%20obtener%20la%20contrase%C3%B1a%20original.)


| política | Restricciones | Contraseña1 | pwScore | Contraseña2 | pwScore | Contraseña3 | pwScore |
| :- | :- | :- | :-: | :- | :-: | :- | :-: |
| Débil |  |  |  |  |  |  |  |
| Media |  |  |  |  |  |  |  |
| Extrema |  |  |  |  |  |  |  |