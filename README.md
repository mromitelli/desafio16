DESAFÍO 16 - INTRODUCCIÓN A LA SEGURIDAD INFORMÁTICA

USER ACCOUNT CONTROL
1.	Configurar User Account Control para que solicite confirmación siempre.
Desde el User Account Control Settings se puede configurar que siempre se solicite confirmación cuando se hagan instalaciones de software o cambios en la maquina; o en las configuraciones de Windows.
 
REMOTE DESKTOP
2. Habilitar el acceso por Remote Desktop.
3. Crear una cuenta de usuario llamada bonustrack.
4. Asignar permisos básicos (users) al usuario creado anteriormente.
5. Conceder privilegios al usuario bonustrack para tener la posibilidad de iniciar sesión a través de Remote Desktop. 

Comprobación del ingreso con el usuario bonustrack por conexión a escritorio remoto.
 

 

DIRECTIVAS DE SEGURIDAD
6. Habilitar la complejidad de contraseñas.
7. Configurar:
a. No expiren las contraseñas.
 

b. Contraseñas con 10 caracteres de longitud.
c. Evitar la reutilización de las últimas 10 contraseñas.
d. Bloqueo de cuentas luego de 7 intentos fallidos.
e. Desbloqueo automático después de 10 minutos.   
Todas estas configuraciones se hacen desde el Local Security Policy.

WINDOWS DEFENDER
8. Habilitar Windows Defender (en el caso de que no se encuentre presente).
Verificaciones de Windows Defender Firewall desde Control Panel  System and Security
 
9. Descargar raffle.exe desde:
https://mega.nz/file/y24W2TSD#e6GxenMG4RGTzCsS9J9R2KlSFp9uvb13-qbzjNxvv64.
10.Verificar que Windows Defender lo haya detectado
 

11.Subir el archivo descargado al sitio VirusTotal.
https://www.virustotal.com/gui/home/upload
12.Analizar y mostrar el resultado.
60/74 security vendors and no sandboxes flagged this file as malicious

 

HASHES
13. Crear un archivo de texto plano con el nombre prueba1.txt en donde el contenido del archivo sea únicamente EducaciónIT.
14. Calcular los valores hash del archivo con diferentes algoritmos, utilizando la herramienta HashMyFiles.
https://www.nirsoft.net/utils/hash_my_files.html
15. Crear un segundo archivo, agregar el siguiente contenido EducacionIT1, agregando un 1 (uno) al final, y guardar con el nombre prueba2.txt.
16. Volver a calcular los hashes y verificar si los mismos han cambiado con respecto a los anteriores. 
Se descarga e instala la aplicación. Posteriormente con los archivos ya creados se utilizan para el análisis en el HashMyFiles:
 
 
Resultado: Los hash del archivo han cambiado con respecto a los anteriores. 



VOLÚMENES DE DISCOS CIFRADOS
17. Usar VeraCrypt para crear un volumen de disco cifrado de 10 MB que utilice el algoritmo de Hash SHA 512 y el algoritmo de cifrado AES.
https://www.veracrypt.fr/en/Downloads.html
18. Montar el volumen cifrado.
19. Almacenar el archivo prueba1.txt del ejercicio 13 dentro del volumen.
20. Desmontar el volumen, volver a montarlo y verificar si los archivos se encuentren intactos.
Primero hacemos la partición del disco:
 
El administrador de discos reconoce el volumen:
 
	Con la aplicación VeraCrypt instalada ya se puede hacer el proceso de 
	Asistente de Creación de Volumenes VeraCrypt: Cifrar partición/unidad secundaria.
	Tipo de Volumen: Volumen VeraCrypt común.
	Modo de creación de volumen: Cifrar partición conservando datos.
	Generar una contraseña de volumen.
	Modo de borrado: Ninguno (configuración rápida).
	Finalmente cifrar.

 
 
Después de este cambio ya no aparece el nombre que originalmente le habíamos dado al volumen.
	Montado con VeraCrypt:
	Seleccionar un volumen (ej.H)
	Seleccionar dispositivo.
	Seleccionar la partición correspondiente y colocar la contraseña para montar.

 
En este caso se montó el D en el H.

 
Ahora está disponible y los archivos son accesibles.
 

Al desmontar y montar se mantiene intacto el archivo.


ALMACENAMIENTO DE CONTRASEÑAS
21. Usar KeePassXC para crear una base de datos de contraseñas.
https://keepassxc.org/download/#windows
22. Almacenar credenciales con los siguientes datos:
a. Usuario: Prueba1.
b. Contraseña: “AlgoSuperSeguro.7823”
23. Cerrar KeePassXC y volver a abrir.
24. Verificar si la contraseña que se ha almacenado esté presente en la base

 

Después de Cerrar KeePassXC y volver a abrir la contraseña que se ha almacenado está presente en la base:
 


Para el desafío generé una VM (AWS EC2) haciendo las pruebas en un entorno aislado y realizando las configuraciones de seguridad necesarias. Posterior a la práctica eliminé todos los recursos utilizados en AWS.
