Agustin Bergomi

A continuacion se mencionan brevemente algunos pasos realizados para realizar los puntos 1 y 2 del Trabajo Practico.


Se instaló MariaDB, se habilitó el servicio con systemctl enable mariadb, se inició con systemctl start mariadb, y se verificó que el servicio estaba funcionando correctamente.
<img width="700" alt="5" src="https://github.com/user-attachments/assets/02383601-cbb2-41f2-8013-7a79a5871e09" />

Se probó el funcionamiento del servidor Apache en el navegador, y se confirmó que el contenido del servidor web estaba disponible desde la máquina anfitriona.
<img width="700" alt="4" src="https://github.com/user-attachments/assets/87c9d15b-c780-45df-9223-47161663c045" />


Se instaló el servidor Apache2 utilizando el comando apt install apache2, se inició el servicio con systemctl start apache2, y se verificó su estado mostrando que estaba en ejecución.
<img width="700" alt="3" src="https://github.com/user-attachments/assets/ab9b6740-daa3-4fd6-8269-5a13b83eb3a4" />


Se descargaron los archivos index.php y logo.png desde un repositorio en GitHub utilizando el comando wget, y se verificó que se guardaron correctamente en el directorio /var/www/html/.
<img width="700" alt="2" src="https://github.com/user-attachments/assets/cdae9461-f0de-42cb-9cbd-12e55ea333dc" />


Se intentó iniciar sesión en Debian con distintos usuarios (vboxuser, palermo) y finalmente se accedió correctamente como root usando la clave configurada.
<img width="700" alt="1" src="https://github.com/user-attachments/assets/57d878e8-2f90-4ee9-a97b-612c453d1c3d" />


Se descargó el archivo db.sql desde GitHub utilizando wget, confirmando que se guardó correctamente. Luego, se accedió a MariaDB con el comando mysql -u root.
<img width="1630" alt="6" src="https://github.com/user-attachments/assets/e308084a-1ef3-4aa1-aab7-cf5394b87f5e" />

Se creó una base de datos llamada infotp dentro de MariaDB con el comando:

sql
Copy
Edit
CREATE DATABASE infotp;
y se verificó el acceso a dicha base.
<img width="1092" alt="7" src="https://github.com/user-attachments/assets/c168c0ad-69ea-4bc9-a162-ed32d95e4528" />

Hubo intentos de cargar y manipular datos en la base de datos infotp. Se corrigieron errores de sintaxis SQL y se verificaron tablas y datos utilizando USE y SHOW TABLES.
<img width="1101" alt="8" src="https://github.com/user-attachments/assets/a79c88b9-e050-4bec-bb1a-ae02d8bb2ed2" />

Se consultaron tablas como modulos y notas dentro de la base de datos infotp, confirmando que los datos se cargaron correctamente, incluyendo información detallada de módulos y calificaciones.
<img width="876" alt="9" src="https://github.com/user-attachments/assets/5313b1fe-ca54-48da-a398-943778b7007f" />

Se actualizó el archivo /etc/hosts, agregando el nombre Server-TP vinculado a la IP local (127.0.1.1). Esto aseguró que el nombre del servidor estuviera correctamente configurado para resolver localmente.
<img width="692" alt="10" src="https://github.com/user-attachments/assets/2e8918b0-1a6a-4cdf-bb2b-f47a6cf317e1" />

Se intentó subir el archivo comprimido root.tar.gz a un servicio de almacenamiento con curl, pero arrojó errores indicando que no pudo leer los datos locales correctamente. Se verificaron los archivos en el directorio /root.
<img width="1196" alt="11" src="https://github.com/user-attachments/assets/3068ba0d-2d5f-4381-9986-9b1b5ef29663" />

Se usó el comando lsblk para listar los discos y particiones disponibles. Luego, se ejecutó fdisk /dev/sdc para configurar un nuevo disco, seleccionando opciones como tipo de partición primaria (p) y asignando un número de partición.
<img width="1294" alt="12" src="https://github.com/user-attachments/assets/d8b5ca7e-79e2-49af-9049-970d95bc1cfe" />

Se utilizó el comando du -sh /* | sort -h para listar los directorios en el sistema junto con su tamaño, ordenándolos de menor a mayor, y se verificaron los recursos de almacenamiento disponibles.
<img width="1291" alt="13" src="https://github.com/user-attachments/assets/71922a40-b278-45c0-ae4e-cbb7d9e62c29" />

Se ejecutó el instalador de VirtualBox Guest Additions con VBoxLinuxAdditions.run. Se verificaron dependencias y se mostró un mensaje sobre módulos del kernel que no se pudieron cargar completamente.
<img width="1264" alt="14" src="https://github.com/user-attachments/assets/80fef51b-4873-4c97-b60f-7756bd16cffd" />






