# Comandos básicos

## Configuración

|                |Comando                          |
|----------------|-------------------------------|
|Verificar versión|`git --version`|
|Saber sobre un comando|`git help "comando"`            |
|Nombre global|`git config --global user.name "Nombre"`|
|Email global|`git config --global user.email "nuestro@email.com"`|
|Ver configuración global y alias|`git config --global -l`|
|Ver configuración global|`git config --global -e`|
|Ver configuración local y alias|`git config -l`|
|Ver configuración local|`git config -e`|

Al realizar estas configuraciones ya no tendríamos que configurar los usuarios de git cada vez que realicemos **commits** o hagamos **push**.

## Iniciando un proyecto

|                |Comando                          |
|----------------|-------------------------------|
|Inicializar un repositorio|`git init`|

## Verificar estado de los archivos

|                |Comando                          |
|----------------|-------------------------------|
|Verificar cambios que se han realizado|`git status`|
|Ver los archivos que tuvieron cambios|`git status -s`|
|Ver archivos con cambios junto con la rama actual|`git status -s -b`|

## Agregar o quitar archivos antes del commit

|                |Comando                          |
|----------------|-------------------------------|
|todo|`git add .`|
|todo lo q se modificó|`git add -A`|
|archivos con cierta extensión en el directorio actual|`git add *.png`|
|archivos con cierta extensión de **TODO** el proyecto|`git add "*.png"`|
|Agregar todos los archivos|`git add --al`|
|archivos en una carpeta con cierta extensión|`git add pdfs/*.pdf`|

## Volver al ultimo commit si tocaste algo guardas cerrraste y no sirve el cntrl + z 😀🤬👿

|                |Comando                          |
|----------------|-------------------------------|
|Volver al ultimo commit|`git checkout -- .`|
|Volver al ultimo commit duramente eliminando todo hasta ese commit|`git reset --hard HEAD😍`|

## Revertir commit

|                |Comando                          |
|----------------|-------------------------------|
|Quitar del stage todos los archivos|`git reset .`|
|Quitar del stage archivos con cierta extensión|`git reset *.xml`|
|Quitar del stage archivo en específico|`git reset HEAD "archivo"`|
|Quitar del STAGE archivo que tenía commit sin eliminar nada|`git reset --soft "HEAD^ o el id obtenido con git lg"`|
|Regresar a un commit sin quitar los cambios que tienen los archivos|`git reset --mixed "id"`|
|Regresar a un commit y pone los archivos como estaban en ese entonces|`git reset --hard "id"`|

## Recuperar cambios después de un `git reset`

|                |Comando                          |
|----------------|-------------------------------|
|Mostrar todas las acciones que se han hecho en el repositorio (commits, resets, etc)|`git reflog`|
|Recuperar los cambios luego de haber hecho un **reset (..hard)**, viendo el id del **git reflof**|`git reset --hard "id del commit al que queremos volver"`|

## Revisar cambios que hemos hecho

|                |Comando                          |
|----------------|-------------------------------|
|Ver cambios que se hicieron en los archivos|`git diff`|
|Ver cambios que se hicieron en los archivos incluso estando en el stage|`git diff --staged`|

## Guardar commits

|                |Comando                          |
|----------------|-------------------------------|
|Guardar los cambios|`git commit -m "Mensaje"`|
|Agregar todos los archivos al state y hacer el commit en una línea|`git commit -am "Mensaje"`|

Se recomienda hacer commits específicos, esto permitirá hacer **checkouts** más fácilmente sin necesidad de afectar otras secciones de nuestro código que están bien.

## Modificar commit

|                |Comando                          |
|----------------|-------------------------------|
|Modificar mensaje de commit (sin/con haber hecho push)|`git commit --amend -m "Mensaje correcto"`|

## Revertir cambios

|                |Comando                          |
|----------------|-------------------------------|
|Regresar los cambios al último commit|`git checkout -- .`|
|Regresar los cambios al último commit de cierto archivo|`git checkout -- "archivo"`|

## Ver historial de commits

|                |Comando                          |
|----------------|-------------------------------|
|Ver commits (orden descendiente)|`git log`|
|Hacer log con hash (id) corto|`git log --oneline`|
|Hacer log con hash (id) corto en forma de listado|`git log --oneline --decorate --all --graph`|

## Configuración de archivos desde Git

### - Desde la terminal

|                |Comando                          |
|----------------|-------------------------------|
|Renombrar archivos|`git mv nombre-actual-archivo.txt nombre-que-tendra.txt`|
|Eliminar archivos|`git rm nombre-archivo.txt`|

Después de realizar estos comandos se deben hacer los commits para guardar los cambios, por que ya estan en el STAGE 😎.

### - Desde el editor

Se renombra desde el editor de preferencia, al hacer `git status` Git dirá que eliminamos un archivo y hemos creado otro, para corregir esto y que Git sepa que es una actualización en el nombre debemos hacer lo siguiente:

|                |Comando                          |
|----------------|-------------------------------|
|Actualizar todo|`git add -u`|
|Agregar todo|`git add -A`|

En este punto ya reconoce que el archivo fue renombrado. Ya después de esto podremos hacer el commit sin problemas.

Para eliminar simplemente borramos el archivo desde el editor y ejecutar los siguientes comandos:

|                |Comando                          |
|----------------|-------------------------------|
|Actualizar todo|`git add -u`|

Ya en este punto habrá detectado que el archivo fue eliminado y podremos hacer commit.

## Ignorar archivos

Creamos un archivo con nombre **.gitignore** y escribimos el nombre del archivo/carpeta que no queremos agregar a nuestro repositorio (para todos los archivos con una extensión en particular escribimos *.extensión y para carpetas node_modules/).

## Crear alias

|                |Comando                          |Ejemplo|
|----------------|-------------------------------|-------------------------------|
|Crear alias|`git config --global alias."alias" "codigo"`|`git config --global alias.lg "log --oneline --decorate --all --graph"`|
|Otro ejemplo|`git config --global alias."alias" "codigo"`|`git config --global alias.s "status -s -b"`|
|Ver listado de datos globales y alias|`git config --global -l`|Sin ejemplo|

Estos alias se crean con el fin de simplificar las instrucciones que le damos a Git.

## Errores

|                |Comando                          |
|----------------|-------------------------------|
|Si se presenta problema con el CRLF|`git config core.autocrlf true`|
|Si se presenta problema de warning: LF will be replaced by CRLF|`git config core.autocrlf true`|

# Ramas

Una rama es una línea de tiempo de commits, estas nos ayudarán cuando queramos agregar funciones a nuestro programa que pueden o no unirse al programa principal.

|                |Comando                          |
|----------------|-------------------------------|
|Crear rama|`git branch nombre-rama`|
|Crear rama y moverse a ella en un comando 😎|`git checkout -b nombre-rama`|
|Ver ramas (la verde es la rama en la que estamos actualmente)|`git branch`|
|Ver ramas con commits|`git branch -v`|
|Ver ramas con ramas remotas|`git branch -a`|
|Ver ramas con commits y ramas remotas|`git branch -av`|
|Cambiar de rama|`git checkout nombre-rama`|
|Ver diferencias entre ramas|`git diff rama-1 master-o-rama-2`|
|Eliminar rama (hacer luego de hacer merge)|`git branch -d nombre-rama`|
|Eliminar rama forzosamente|`git branch -d nombre_rama -f`|
|Eliminar rama |`git branch -D nombre-rama`|

## Ramas remotas

|                |Comando                          |
|----------------|-------------------------------|
|Ver ramas remotas|`git branch -r`|
|Ver ramas remotas y locales|`git branch -a`|
|Ver ramas remotas y locales con commits|`git branch -av`|
|Crear subir rama remota a github|`git push origin nombre-rama`|
|Eliminar rama remota|`git push origin :nombre-rama`|

## Ramas remotas con pull

|                |Comando                          |
|----------------|-------------------------------|
|Ver ramas remotas y locales y HEAD|`git branch -avvv`|
|Crear rama remota😍|`git pull origin nombre-rama`|
|Eliminar rama remota|`git push origin :nombre-rama`|

## Ramas remotas con fetch

|                |Comando                          |
|----------------|-------------------------------|
|Ver ramas remotas y locales|`git branch -a`|
|Ver ramas remotas|`git branch -r`|
|Crear rama remota|`git fetch origin nombre-rama`|
|Eliminar rama remota|`git push origin :nombre-rama`|
|Eliminar rama eliminado en github remotamente|`git remote prune origin`|

## Merge Fast-Forward

Para hacer un merge debemos estar en la rama master, este tipo de merge sucede cuando sólo se hacen modificaciones en una rama.

|                |Comando                          |
|----------------|-------------------------------|
|Unir ramas|`git merge rama-a-unir`|

## Merge automático

Se realiza cuando hay cambios en ambas ramas pero no hay conflicto de sobreescritura.

|                |Comando                          |
|----------------|-------------------------------|
|Unir ramas|`git merge rama-a-unir`|

## Merge con conflictos

Este tipo de merge sucede cuando realizamos cambios en ambas ramas y estos pueden sobreescribirse.

|                |Comando                          |
|----------------|-------------------------------|
|Unir ramas|`git merge rama-a-unir`|

En este punto tendremos que hacer la modificación manualmente, para ello quitamos las etiquetas
    (<<<<<<<<<<<HEAD, ============, 
    >>>>>>>>>>>>>>) 
y hacemos el commit.

## Tags

Son una referencia a un commit específico, se usan para guardar releases, usualmente se guardan usando número de versiones.
Se pueden descargar de GitHub.
|                |Comando                          |
|----------------|-------------------------------|
|Crear tags|`git tag nombre-o-versión-tag`|
|Crear tags con versión y mensaje|`git tag -a v1.0.0 -m "mensaje"`|
|Crear tag en commit anterior|`git tag -a v0.1.0 hash-commit -m "mensaje"`|
|Ver tags (sólo muestra la versión o nombre que le dimos)|`git tag`|
|Borrar tags|`git tag -d nombreTag`|
|Ver + detalle del tag|`git show nombre_tag`|
|Ver mensaje y demas de tags|`git show v1.0.0`|
|Subir tags a repositorio remoto|`git push origin --tags`|
|Subir tags a repositorio remoto|`git push --tags`|

## Traer cambios de repositorio remoto

|                |Comando                          |
|----------------|-------------------------------|
|Traer cambios de repositorio remoto|`git pull`|
|Traer cambios de repositorio remoto con todas las ramas|`git pull --all`|
|Traer cambios de repositorio remoto con todas las ramas y tags|`git pull --all --tags`|

## Git stahs

Git stash: guarda los cambios que no hemos hecho commit, es decir, los cambios que no están en el área de preparación. Espacio temporal.
|                |Comando                          |
|----------------|-------------------------------|
|Guardar cambios|`git stash`|
|Ver cambios guardados|`git stash list`|
|Recupera cambio y elimina|`git stash pop`|
|borrar todos los stahs|`git stash clear`|
|Recuperar cambios  de un stash|`git stash apply stash@{2}`|
|borrar un stahs|`git stash drop stash@{2}`|
|ver a detalle un stahs|`git stash show stash@{2}`|
|Guardar cambios con nombre|`git stash save "mensaje"`|

## rebase

rebase: actualiza nuestra rama del master

|                |Comando                          |
|----------------|-------------------------------|
|Rebase|`git rebase nombre-rama`|
|Rebase con squash|`git rebase -i nombre-rama`|
luego del rebase se realiza el: `git merge rama y luego borrar la rama: git branch -d nombre_rama`

`git rebase -i HEAD~`