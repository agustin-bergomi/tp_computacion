Materia: Computacion Aplicada

Alumno: Agustin Bergomi

Tema: Trabajo Practico Integrador


Abstract

En este trabajo práctico se configuró un servidor virtualizado con Debian, realizando diversas tareas que incluyeron el blanqueo de la clave de root, la configuración del hostname y la resolución de nombres locales. Se instaló y configuró un servidor web Apache junto con MariaDB para la gestión de bases de datos, descargando archivos esenciales desde un repositorio remoto y verificando su correcto funcionamiento. También se realizaron ajustes en particiones, almacenamiento y herramientas de VirtualBox para optimizar el entorno. A pesar de algunos errores en operaciones como la subida de archivos con curl, los objetivos principales del servidor fueron cumplidos exitosamente.

---

A continuacion se inlcuyen imagenes de algunos pasos realizados para el punto 1 y 2 del trabajo practico:

**Se instaló MariaDB**  
Se instaló MariaDB utilizando el comando `apt install mariadb-server`. Luego, el servicio se habilitó con `systemctl enable mariadb` y se inició con `systemctl start mariadb`. Se verificó el estado del servicio con `systemctl status mariadb`, confirmando que estaba funcionando correctamente.  

<img width="700" alt="5" src="https://github.com/user-attachments/assets/02383601-cbb2-41f2-8013-7a79a5871e09" />

---


**Prueba del servidor Apache**  
Se probó el funcionamiento del servidor Apache accediendo desde el navegador de la máquina anfitriona. Esto confirmó que el contenido del servidor web estaba disponible y sirviendo correctamente los archivos configurados. Se utilizó la URL `http://<IP-Servidor>` para la prueba.  

<img width="700" alt="4" src="https://github.com/user-attachments/assets/87c9d15b-c780-45df-9223-47161663c045" />

---

**Instalación de Apache2**  
Se instaló Apache2 con el comando `apt install apache2`, habilitando y arrancando el servicio con `systemctl enable apache2` y `systemctl start apache2`. Luego, se verificó su estado usando `systemctl status apache2`, observando que estaba activo y funcionando correctamente.  

<img width="700" alt="3" src="https://github.com/user-attachments/assets/ab9b6740-daa3-4fd6-8269-5a13b83eb3a4" />

---

**Descarga de archivos para el servidor web**  
Se descargaron los archivos `index.php` y `logo.png` desde un repositorio de GitHub utilizando `wget`. Los comandos ejecutados fueron:  
```bash
wget https://raw.githubusercontent.com/agustin-bergomi/infotp/main/index.php  
wget https://raw.githubusercontent.com/agustin-bergomi/infotp/main/logo.png  
```  
Estos archivos se almacenaron en `/var/www/html/` y se verificaron con `ls`.  

<img width="700" alt="2" src="https://github.com/user-attachments/assets/cdae9461-f0de-42cb-9cbd-12e55ea333dc" />

---

**Acceso root al sistema**  
Se intentó iniciar sesión en Debian con diferentes usuarios (`vboxuser`, `palermo`) y finalmente se accedió correctamente como root utilizando la clave configurada previamente. Esto permitió obtener acceso completo al sistema.  

<img width="700" alt="1" src="https://github.com/user-attachments/assets/57d878e8-2f90-4ee9-a97b-612c453d1c3d" />

---

**Descarga y carga del archivo SQL**  
Se descargó el archivo `db.sql` desde GitHub con el comando `wget`, confirmando su correcta descarga con `ls`. Luego, se accedió a MariaDB con el comando `mysql -u root`, preparando el entorno para importar la base de datos.  

<img width="1630" alt="6" src="https://github.com/user-attachments/assets/e308084a-1ef3-4aa1-aab7-cf5394b87f5e" />

---

**Creación de la base de datos**  
Dentro de MariaDB, se creó la base de datos `infotp` con el comando:  
```sql
CREATE DATABASE infotp;
```  
Luego, se verificó el acceso a la base de datos recién creada utilizando el comando `USE infotp`.  

<img width="1092" alt="7" src="https://github.com/user-attachments/assets/c168c0ad-69ea-4bc9-a162-ed32d95e4528" />

---

**Manipulación de datos en MariaDB**  
Se realizaron intentos de manipular datos en la base de datos `infotp`, incluyendo la importación de un archivo SQL y consultas. Se corrigieron errores de sintaxis y se ejecutaron comandos como `SHOW TABLES` para verificar las tablas existentes.  

<img width="1101" alt="8" src="https://github.com/user-attachments/assets/a79c88b9-e050-4bec-bb1a-ae02d8bb2ed2" />

---

**Consultas a las tablas**  
Se ejecutaron consultas a las tablas `modulos` y `notas` dentro de la base de datos `infotp`. Esto confirmó que los datos se cargaron correctamente, incluyendo detalles sobre módulos académicos y calificaciones de estudiantes.  

<img width="876" alt="9" src="https://github.com/user-attachments/assets/5313b1fe-ca54-48da-a398-943778b7007f" />

---

**Actualización del archivo /etc/hosts**  
El archivo `/etc/hosts` fue modificado para incluir la línea:  
```plaintext
127.0.1.1    Server-TP  
```  
Esto vinculó el nombre del servidor `Server-TP` a la IP local, garantizando una resolución de nombres adecuada.

<img width="692" alt="10" src="https://github.com/user-attachments/assets/2e8918b0-1a6a-4cdf-bb2b-f47a6cf317e1" />

---

**Intento de subir archivo comprimido**  
Se intentó subir el archivo `root.tar.gz` a un servicio externo con el comando `curl`, pero se encontraron errores relacionados con la lectura de datos locales. El directorio `/root` fue verificado para confirmar la existencia del archivo.  

<img width="1196" alt="11" src="https://github.com/user-attachments/assets/3068ba0d-2d5f-4381-9986-9b1b5ef29663" />

---

**Configuración de particiones**  
Se listaron los discos y particiones disponibles con `lsblk`. Luego, se utilizó `fdisk /dev/sdc` para crear una nueva partición primaria, asignándole un número y tipo específico.  

<img width="1294" alt="12" src="https://github.com/user-attachments/assets/d8b5ca7e-79e2-49af-9049-970d95bc1cfe" />

---

**Verificación de uso de almacenamiento**  
Se utilizó el comando `du -sh /* | sort -h` para listar los tamaños de los directorios del sistema, ordenándolos de menor a mayor. Esto permitió identificar el uso de almacenamiento y optimizar recursos.  

<img width="1291" alt="13" src="https://github.com/user-attachments/assets/71922a40-b278-45c0-ae4e-cbb7d9e62c29" />

---

**Instalación de VirtualBox Guest Additions**  
Se ejecutó el instalador `VBoxLinuxAdditions.run` para VirtualBox Guest Additions, verificando la instalación y las dependencias. Algunos módulos del kernel no pudieron ser cargados completamente, según los mensajes del instalador.  

<img width="1264" alt="14" src="https://github.com/user-attachments/assets/80fef51b-4873-4c97-b60f-7756bd16cffd" />

---

