# Instalacion

`sudo apt install mariadb-serve`<br>
`sudo mysql_secure_installation`<br>
- como al inicio root no tiene pass solo enter<br>
- remove anonymous users? Y<br>
- disallow root login remotely? Y<br>
- remove test database and access to it? Y<br>
- reload privilege tables now? Y<br>


# Configuracion

`sudo mysql` conecta a mariadb<br>
`GRANT ALL ON *.* TO 'nombreusuario'@'localhost' IDENTIFIED BY 'contraseña' WITH GRANT OPTION;` para crear un nuevo usuario con contraseña<br>
`FLUSH PRIVILEGES;` para reiniciar la tabla para reconocer el nuevo usuario<br>
`mysql -u nombreusuario -p` para conectarse con el usuario que ha creado, al dar enter le pide la contraseña con la que se creo<br>


# Comandos linux

`mysql --version` para ver la version de mariadb instalada<br>
`sudo systemctl status mariadb` para ver si esta corriendo mariadb<br>


# Comandos mariadb

`SHOW VARIABLES WHERE Variable_name = 'port';` para ver el puerto que esta utilizando<br>
`create database nombre;` para crear una base de datos<br>


# Conexion administrador de bases de datos (DBeaver)

se puede seguir con comandos o se puede seguir con un administrador de base de datos como dbeaver en el que se realiza:<br>
- una nueva conexion a mariadb<br>
- ip: localhost<br>
- puerto: el que muestra en la paso anterior, por lo general es 3306<br>
- usuario y contraseña creados anterior mente<br>