# Instalacion

`sudo apt install mariadb-serve`
`sudo mysql_secure_installation`
- como al inicio root no tiene pass solo enter
- remove anonymous users? Y
- disallow root login remotely? Y
- remove test database and access to it? Y
- reload privilege tables now? Y


# Configuracion

`sudo mysql` conecta a mariadb
`GRANT ALL ON *.* TO 'nombreusuario'@'localhost' IDENTIFIED BY 'contraseña' WITH GRANT OPTION;` para crear un nuevo usuario con contraseña
`FLUSH PRIVILEGES;` para reiniciar la tabla para reconocer el nuevo usuario
`mysql -u nombreusuario -p` para conectarse con el usuario que ha creado, al dar enter le pide la contraseña con la que se creo


# Comandos linux

`mysql --version` para ver la version de mariadb instalada
`sudo systemctl status mariadb` para ver si esta corriendo mariadb


# Comandos mariadb

`SHOW VARIABLES WHERE Variable_name = 'port';` para ver el puerto que esta utilizando
`create database nombre;` para crear una base de datos


# Conexion administrador de bases de datos (DBeaver)

se puede seguir con comandos o se puede seguir con un administrador de base de datos como dbeaver en el que se realiza:
- una nueva conexion a mariadb
- ip: localhost
- puerto: el que muestra en la paso anterior, por lo general es 3306
- usuario y contraseña creados anterior mente