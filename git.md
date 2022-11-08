# Configuraciones

`git config --list` para ver las configuraciones<br>
`git config --global user.name "kevinsoto"` cambia nombre en configuracion global de git<br>
`git config --global user.email "kevinsoto@correo.co"` para cambiar o asignar correo<br>
`git config pull.rebase false` merge (the default strategy)<br>
`git config pull.rebase true` rebase<br>
`git config pull.ff only` fast-forward only<br>
`git remote add origin urlhttpquevaaponer` para establecer el origin<br>
`git remote -v` para ver el origin asociado<br>
`git remote set -url origin porloquesevaacambiar` para cambiar el origin<br>
`git config --global alias.nombre "shortlog -sn"` crea un alias nombre con esas instrucciones<br>
`git remote add upstream urlhttpdelrepo` para añadir otra fuente de datos con otro nombre, upstream puede ser otro nombre, por lo general se usa con los padres del fork<br>
`git blame --help` muestra toda la informacion del comando blame, --help se puede usar con todos los comandos git<br>


# Historico y busquedas

## Log y reflog
`git log archivo.txt` para ver los commits del archivo<br>
`git log --all --graph --decorate --oneline` para ver los logs graficamente<br>
`git log --stat` dice cuantos cambios hay en cada commit<br>
`git log -S "palabraabuscar"` para buscar una palabra en los commits<br>
`git reflog` muestra todos los commits sin importar uno donde se encuentre<br>

## Blame
`git blame arachivo.php` muestra quien hizo cada linea<br>
`git blame -c archivo.php` lo muestra identado<br>
`git blame archivo.php -L35,54` muestra quien hizo esas lineas, linea por linea<br>

## Shortlog
`git shortlog` muestra los commits realizados por cada persona<br>
`git shortlog -sn` muestra la cantidad por persona<br>
`git shortlog -sn --all --no-merges` muestra la cantidad de commits asi esten borrados pero no los merges<br>

## Grep
`git grep color` muestra los archivos donde se ha usado la palabra color<br>
`git grep -n color` muestra la linea<br>
`git grep -c color` dice cuantas veces se ha usado esa palabra en cada archivo<br>

## Otros
`git show archivo.txt` muestra los cambios que se le han hecho al archivo<br>
`git diff` muestra las diferencia que hay entre lo que se ha ingresado y lo que hay en el add<br>
`git diff 6e32f40069445249b03e2dd621f32d53f1905947 77a472add779ff5ddb8ad405e04f2cbe4ca09cd1` con los codigos de `git log` muestra las diferencias entre los dos commits. el orden de los commits llamados afecta<br>


# Navegacion

`git reset 4c085b5de682563671f8c7a7a4672328b3bb6e06 --hard` con el log, para pararse en ese commit, con hard elimina todo lo que se haya hecho despues del commit al que se va a ir<br>
`git reset 4c085b5de682563671f8c7a7a4672328b3bb6e06` saca del commit lo posterior<br>
`git checkout 4c085b5de682563671f8c7a7a4672328b3bb6e06 archivo.txt` para pararse en la informacion de ese commit en ese archivo<br>
`git checkout master archivo.txt` se mueve en versiones en el archivo, para guardar los cambios y quedar con la version que esta mirando hacer add y commit<br>
`gitk` muestra ramas visualmente en otra ventana<br>
`git reset --hard HEAD@{2}` se puede usar soft para que quede el stage y todo queda en el add. hard si elimina todo y deja el proyecto en en ese head, tambien se puede usar el hash del commit<br>

# Tags

`git tag -a v0.1 -m "mensaje de la primera version" 5af7c1c` para ponerle un tag a un commit, para manejar versionamientos<br>
`git tag` muestra los tags<br>
`git tag -d nombredeltag` para eliminarlo<br>
`git push origin --tags` para hacerle push a los tags<br>
`git push origin :refs/tags/nombredeltag` para eliminarlo en el repositorio de la nube<br>

# Union

`git fetch` trae los cambios del repositorio remoto git merge une con el directorio del trabajo los dos es lo mismo que un git pull<br>
`git merge nombreramaaunir` para unir  ramas en un nuevo commit, se para en la rama en la que va quedar<br>
`git pull origin master --alow-unrelated-histories` cuando presenta error descargando cambios porque no hay commits relacionados, para forzar el pull<br>
`git rebase ramaprueeba` Rebase pasa lo de una rama a la otra sin que quede historia, mala practica. puede crear muchos conflictos. Se hace primero el rebase en la rama que va a desaparecer y despues en la que va a quedar<br>
`git commit --amend` para agregar lo del stage al commit anterior, se puede cambiar el mensaje, se abre vim para editar el comentario<br>
`git cherry-pick hashdelcommit` parado en la rama que quiere quedar trae un commit de otra rama (solo el commit)<br>

# Organizacion y limpieza

## Stash
`git stash list` para ver lo que quedo en stash<br>
`git stash pop` trae lo del stash<br>
`git stash drop` para eliminar el stash<br>

## Clean
`git clean --dry-run` muestra los archivos que se podrian eliminar, los que no estan en en stage ni en commit<br>
`git clean -f` elimina los archivos<br>

## Branch
`git branch -r` para ver las ramas del servidor<br>
`git branch -a` para verlas todas<br>

# Conceptos

- FORK: para cuando un repo es publico pero no puedo hacer push porque no tengo permisos. hago una bifurcacion, clono esa bifurcacion, realizo los cambios ahi y si se requiere hacer un merge con el proyecto original se crea un pull request(github)<br>
