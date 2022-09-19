## Comandos

`ls` lista lo que hay en la ubicacion<br>
`ls -l` lista en forma vertical, con mas informacion (permisos)<br>
`ls -lh` lista para humanos con peso en K<br>
`ls -la` lista todos los archivos incluyendo ocultos (. adelante)<br>
`ls -lha` ver archivos incluyendo ocultos y permisos, los que estan en verde tienen permisos de ejecucion<br>
`tree` muestra todos los archivos en arbol<br>

`cd nombre` ingreesa a la carpeta<br>
`cd ..` para devolver<br>

`clear` limpia pantalla<br>
`ctrl + l` limpia pantalla<br>
`pwd` implimir la ruta de donde esta ubicado<br>
`type comando` dice que tipo es, si es alias o donde esta
`help comando` nos da informacion del comando<br>
`man comando` muestra el manual del comando<br>
`whatis comando` da una descripcion resuminda del comando<br>
`which code` da la ubicacion de donde esta alojado si es un binario (busca en las variables de entorno)<br>
`curl www.google.com` trae informacion del front de la red y la muestra<br>
`wget www.google.com` trae un archivo del front de la pagina y lo guarda en index.html<br>
`chsh -s $(which zsh)` cambia  a zsh (change shell)<br>

`mkdir "nombre archivo"` crea un nuevo directorio, comillas para espacio en el nombre<br>
`touch nombre.extension` crear archivo<br>
`cp nombrearchivoacopiar nombrecopia` copiar archivo<br>
`mv nombrearchivo ubicacion` mover archivo<br>
`mv nombrearchivo nuevonombre` cambiar nombre archivo<br>
`rm nombrearchivo` eliminar archivo<br>
`rm -r nombrecarpeta` eliminar carpeta<br>
`cat nombre` ver archivo<br>
`cat archivo.txt archivo2.txt` muestra concatenacion<br>
`cat > nombrearchivo` para escribir en archivo, control+d para guardar y cerrar<br>
`head nombrearchivo` muestra las primeras 10 lineas del archivo<br>
`head nombrearchivo -n 15` muestra las primeras 15 lineas del archivo<br>
`tail nombrearchivo` muestra las ultimas 10 lineas del archivo<br>
`tail nombrearchivo -n 15` muestra las ultimas 15 lineas del archivo<br>
`less nombrearchivo` abre visualizacion del archivo<br>
    `/palabra` busca la palabra en el archivo<br>
    `q` salir<br>
`xdg-open nombrearchivo` abre el archivo con el programa predeterminado<br>
`nautilus .` abre la carpeta<br>
`ln -s Documents/APP Desarrollo` crea un link simbolico con el nombre Desarrollo,link simbolico, acceso directo <br>

## Wildcards

`ls *.txt` terminados en .txt<br>
`ls datos*` que inicien con datos<br>
`ls datos??` que inicien con datos y tengan 2 caracteres despues<br>
`ls [[:upper:]]*` iniciadas en mayuscula, busca con dos directorios de profundidad<br>
`ls -d [[:lower:]]*` iniciadas en minuscula solo en el directorio actual<br>
`ls -d [[:upper:]]*` iniciadas en mayuscula solo en el directorio actual<br>
`ls [ad]*` muestra los iniciados con a o con d<br>
`ls [[:digit:]]*` para buscar empezados con numero<br>

## Redirecciones

standar input: 0
standar output: 1
standar error: 2

`ls nombrecarpeta > archivo.txt` guarda lo que hay en la carpeta en archivo, si archivo no existe lo crea, si existe lo sobreescribe<br>
`ls nombrecarpeta >> archivo.txt` concatena lo que hay en archivo adicionandole lo que trae ls nombrecarpeta<br>
`ls carpetainexistente 2> archivo.txt` guarda la salida de standar error en archivo<br>
`ls carpetainexistente > archivo.txt 2>&1` guarda en archivo sea que salga un error o que traiga el listado<br>
`|` hace que el output del anterior se vuelva input del siguiente<br>
`ls -lh | less` crea la lista y la muestra con less (apta para busqueda)<br>
`ls -lh | tee archivo.txt | less` crea la lista la guarda en el archivo y despues la muestra con less<br>
`ls -lh | sort | tee archivo.txt | less` crea la lista, la ordena, la guarda en el archivo y la muestra con less<br>
`find ./ -type f > todos2.txt && echo "Realizado con exito"` realiza la consulta y guarda la informacion en el archivo todos2 y despues muestra el mensaje<br>
`cowsay "mensaje"` muestra una vaca diciendo el mensaje, cowsay se debe descargar por apt<br>
`lolcat "mensaje"` muestra el mensaje de colores<br>
`cowsay "mensaje" | lolcat` muestra la vaca diciendo el mensaje de colores<br>
`ls; mkdir carpeta; cal lista` crea carpeta, muestra un calendario sincronamente(uno despues de otro)<br>
`ls & date & cal lista` muestra fecha y calendarrio asincronamente(crea los hilos necesarios para que se corra en paralelo)<br>
`mkdir test && cd test` condicinal, se crea la carpeta, si se crea la carpeta de forma adecuada ingrese a ella, si el anterior no se cumple no sigue<br>
`cd carpetainexistente  || echo "mensaje"` muestra el error del primero y sigue con el otro<br>


## Modificar permisos

`-` archivo normal<br>
`d` directorio<br>
`l` link simbolico<br>
`b` bloque especial (informacion de una usb por ejemplo)<br>

|r |w |x |      
|--|--|--|      
|1 |1 |1 |      
|2²|2¹|2⁰|      
|4 |2 |1 |      
=7

|r |- |x |
|--|--|--|
|1 |0 |1 |
|2²|2¹|2⁰|
|4 |0 |1 | 
=5

7 y 5 son numeros octales que vienen de los permisos


`chmod 755 nombrearchivo` modifica los permisos el primer puesto es para el usuario, el segundo para el grupo y el tercero para el mundo<br>
`chmod u-r nombrearchivo` al usuario le quita el permiso para leer<br>
`chmod u+r nombrearchivo` al usuario se le da permiso de leer<br>
`chmod u-x,go=w mitexto.txt` al usuario le quita permiso de ejecucion, a  global y a otros les da permiso de solo lectura<br>
`whoami` muestra el usuario con el que esta trabajando<br>
`id` muestra toda la infomacion de los usuarios<br>
`su root` para cambiar al usuario root<br>
`sudo -i` tambien para pasar a root<br>
`su kevin` para pasar a kevin<br>
`sudo chown -R nombreusuario:  nombrecarpetaOArchivo` cambiar usuario de carpeta<br>
`chmod +x start.sh` dar permisos de ejecucion al archivo start.sh<br>

## Variables de entorno

`printenv` muestra las variables de entorno<br>
`echo $HOME` imprime cual es el home<br>
`echo $PATH` tiene las rutas de los binarios que se ejecutan en el sistema<br>
`code .bashrc` abre con vsc el archivo para editarlo que esta en el home<br>
`PLATZI_MESSAGE="HOLA AMIGOS"` en el archivo bashrc crea la variable de entorno<br>
`PATH=$PATH:/home/Documents` le agrega a la variable $PATH /home/Documents<br>

## Agregar alias

`nano .bashrc` parado en el home<br>
`alias vpn='cd /home/kevin/Documents/APP/vpn && sudo ./start.sh'`<br>
`source .bashrc` actualizar el archivo<br>

`alias l="ls -lh"` hace un alias temporal para la terminal, se elimina cerrando la terminal<br>

## Instalacion de programas

`sudo apt install nodejs`<br>
`sudo apt remove nodejs`<br>

## Busqueda

`find ./ -name file` busca todos los archivos que se llamen file en todas las carpetas<br>
`find ./ -name *.txt` trae todos los txt<br>
`find ./ -type fd -name nombre`  busca archivos file o directorios<br>
`find ./ -type f -name  *.log`<br>
`find ./ -size 20M` todos los mayores a 20M<br>
- GREP: encuentra coincidencias dentro de cualquier archivo<br>
`grep Towers movies.csv` busca todas la lineas que tengan el nombre Towers en el archivo movies<br>
`grep -i the movies.csv` ignore case<br>
`grep -i the movies.csv | less` y lo muestra en less<br>
`grep -c the movies.csv` cuenta el numero de ocurrencias<br>
`grep -ci the movies.csv` cuenta con ignore case<br>
`grep -vi towers movies.csv` los que no tienen towers ignore case<br>

`wc movies.csv` cuenta cuantas palabras tiene el archivo muestra lineas, palabras y bits<br>

## Comprimir archivos

`tar -cvf ejemplo.tar ejemplo` v es de verbose, c de comprimir, f file comprime en .tar la carpeta ejemplo<br>
`tar -cvzf ejemplo.tar.gz ejemplo` comprime en tar gz<br>
`tar -xzvf ejemplo.tar.gz` descomprimir el ejemplo.tar.gz<br>
`zip -r ejemploInZip.zip ejemplo` comprimir en zip<br>
`unzip ejemploInZip.zip` descomprime zip<br>


## Procesos

`ps` muestra los procesos que estan corriendo<br>
`top` muestra los procesos y los recursos que son consumidos, h para ayuda<br>
`kill 2910` se pone el PID el id del proceso para finalizarlo<br>
`htop` muestra con mas detalle `f4` para buscar<br>


## Editores

- `vim index.html` crea el archivo, se presiona la tecla<br>
`i` para insertar<br>
`esc` para navegar dentro del archivo<br>
`/` para buscar<br>
`dd` para eliminar linea estando en normal<br>
`:w` para guardar<br>
`:wq` para guardar y salir<br>

`nano nombre` editar archivo<br>