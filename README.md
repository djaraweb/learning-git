# Resumen de Comandos Git

1. git init
2. git add .
3. git reset . // Quita los archivos del state
4. git commit -m "Descripción del commit"
5. git checkout -- . // recupera los cambios del ultimo commit.
6. git log
7. git commit --amend // Permite editar el nombre del ultimo commit
8. git checkout -b rama-heroes // Crea una rama y se ubica en la rama creada
9. git checkout master
10. get merge rama-heroes
11. git branch -d rama-heroes // Borrar rama indicada
12. git remote add origin https://github.com/djaraweb/learning-git.git // Establecer conexion remota con un repositorio.
13. git branch -M main //Renombrar el nombre del master a main
14. git push -u origin main // Subir los cambios al repositorio
15. git clone https://github.com/djaraweb/learning-git.git
16. git pull // traer informacion del repo remoto al local

# Detalle de Comandos Básicos Git

#### _**Configuración Inicial:**_

```sh
$ git config --global user.name "Deyvi Jara"
$ git config --global user.email djaravirtual@gmail.com
```

#### _**Crea localmente un repositorio:**_

```sh
$ git init
```

#### _**Muestra la configuracion de las variables globales:**_

```sh
$ git config -l
```

#### _**Agrega TODOS los archivos y carpetas que estén en nuestro proyecto al staging area:**_

```sh
$ git add .
```

#### _**Hacer commit a los archivos para que queden guardados en el repositorio:**_

```sh
$ git commit -m "Descripción de Commit"
```

#### _**Realiza un commit directamente al repositorio sin pasar por el staging area:**_

```sh
$ git commit -am "Descripción de Commit"
```

#### _**Se agregan los cambios al ultimo commit previo envio de archivos al staging area (gid add .):**_

```sh
$ git commit --amend
```

#### _**Crea un nuevo branch y automaticamente GIT se cambia al branch creado, clonando el branch desde donde ejecutamos el comando:**_

```sh
$ git checkout -b NombreDeBranch
```

#### _**Nos muestra una lista de los branches que existen en nuestro repositorio:**_

```sh
$ git branch [se muestran todas las ramas locales]
$ git branch -r  [se muestran todas las ramas remotas]
$ git branch -a  [se muestran todas las ramas tanto locales como remotas]
```

#### _**Sirve para moverse entre branches, en este caso vamos al branch que indicamos en el comando:**_

```sh
$ git checkout NombreDeBranch
```

#### _**Hace un merge entre dos branches, en este caso la dirección del merge sería entre el branch que indiquemos en el comando, y el branch donde estémos ubicados:**_

```sh
$ git merge NombreDeBranch
```

#### _**Permite eliminar una rama:**_

```sh
$ git branch -d NombreDeBranch
```

#### _**Nos indica el estado del repositorio:**_

```sh
$ git status
```

#### _**Clona un proyecto de git en la carpeta NombreProyecto:**_

```sh
$ git clone URL/name.git NombreProyecto
```

#### _**Establecer conexión con el repositorio remoto:**_

```sh
$ git remote add origin URL/name.git
$ git remote add origin https://github.com/djaraweb/learning-git.git
```

#### _**Cambiar la conexión del repositorio remoto con HTTPS y SSH:**_

```sh
[Https] $ git remote set-url origin https://github.com/djaraweb/repositorio_github.git
[SSH] $ git remote set-url origin git@github.com:djaraweb/repositorio_github.git
```

#### _**Subir cambios a un repositorio remoto:**_

```sh
$ git push origin NombreDeBranch
$ git push
```

#### _**Bajar cambios a un repositorio local:**_

```sh
$ git pull origin NombreDeBranch
$ git pull
```

#### _**Ver logs y detalle de cambios realizados:**_

```sh
$ git log --all --graph --decorate --oneline => muestra el detalle de commits en arbol.
$ git shortlog -sn => muestra cuantos commit han hecho cada miembros del equipo.
$ git shortlog -sn --all => muestra cuantos commit han hecho cada miembros del equipo hasta los que han sido eliminado
$ git shortlog -sn --all --no-merge => muestra cuantos commit han hecho cada miembros quitando los eliminados sin los merges
$ git reflog => Ver la historia de los commits
```

#### _**Resetear cambios:**_

```sh
$ git reset .   => Quita los archivos del state
$ git reset HEAD ^ --hard   => Volver al ultimo commit perdiendo los cambios actuales, Empezando de cero
$ git reset HEAD ^ --soft => Volver al ultimo commit pero no perder los cambios actuales
$ git reset --soft HashDelHEAD => Te mantiene lo que tengas en staging ahí.
$ git reset --hard HashDelHEAD => resetea absolutamente todo incluyendo lo que tengas en staging.
```

#### _**Eliminar un archivo en la historia de los commits:**_

```sh
$ git rm --cached RutaDelArchivo(IncluyeCarpetas)
```

#### _**Cambiar el usuario a todos los commits de un repositorio:**_

```sh
$ git filter-branch -f --env-filter "
GIT_AUTHOR_NAME='Deyvi Jara'
GIT_AUTHOR_EMAIL='djaravirtual@gmail.com'
GIT_COMMITTER_NAME='Deyvi Jara'
GIT_COMMITTER_EMAIL='djaravirtual@gmail.com'
" HEAD
```
