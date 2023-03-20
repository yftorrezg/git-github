# GitHub

## Comandos basicos

### Configuración

|                |Comando                          |
|----------------|-------------------------------|
|versión|`git --version`|
|Ayuda|`git help "comando"`            |
|Nombre|`git config --global user.name "Nombre"`|
|Email|`git config --global user.email "nuestro@email.com"`|
|Ver configuración global y alias|`git config --global -l`|
|Ver cg|`git config --global -e`|

ultima: se puede entrar normal con ``O``😥averiguar como  salir de la configuración: `:wq!`
Con esto ya no configurararemos usuario/email cada que hagamos **commits** o **push**.

### **Comandos terminal**

- Entrar carpeta:   `cd 'arrastrar carpeta a tm'`
- Entrar.............:           `cd "name folder"`
- Volver.............:           ``cd ..``
- Ver contenido.:    ``ls``
- Ver '' oculto.....: ``ls -al``

#### Crear archivos

- Archivo vacio: ``touch "nombre_archivo"``
- Con contenido: ``echo "contenido_archivo" > "nombre_archivo"``
- Con contenido: ``echo "contenido_archivo" >> "nombre_archivo"``
- Ejemplo..........:`echo "que guapo el fer" > fer.md`

#### Crear carpetas

- Carpeta: ``mkdir "nombre_carpeta"``
- Carpeta con archivos: ``mkdir -p "nombre_carpeta/nombre_carpeta/nombre_archivo"``
- Ejemplo..........: ``mkdir -p "fer/fer/fer.md"``

#### Copiar archivos

|                |Comando                          |
|----------------|-------------------------------|
|Copiar archivo| `cp "nombre_archivo" "nombre_archivo"`|
|ejemplo| `cp -r "fer/fer.md" "fer/fer2.md"`|
|Copiar carpeta| `cp -r "nombre_carpeta" "nombre_carpeta"`|
|ejemplo| `cp -r "fer/fer" "fer/fer2"`|

#### Mover archivos

|                |Comando                          |
|----------------|-------------------------------|
|Mover archivo| `mv "nombre_archivo" "nombre_archivo"`|
|ejemplos| `mv -r "fer/fer.md" "fer/fer2.md"`|
|Mover carpeta| `mv -r "nombre_carpeta" "nombre_carpeta"`|
|ejemplos| `mv -r "fer/fer" "fer/fer2"`|
|ejemplos| `mv valeria/ valeria2/`|
Se usa para renombrar archivos y carpetas.

#### Borrar archivos

|                |Comando                          |
|----------------|-------------------------------|
|Borrar archivo| `rm "nombre_archivo"`|
|ejemplos| `rm fer.py"`|
|Borrar carpeta| `rm -r "nombre_carpeta"`|
|ejemplos| `rm -r valeria/"`|

#### Abrir archivo

|                |Comando                          |
|----------------|-------------------------------|
|Abrir archivo| `open "nombre_archivo"`|
|Abrir carpeta: |`open "nombre_carpeta"`|
|Abrir VSCode| `code`|

#### Ver el historial de comandos

|                |Comando                          |
|----------------|-------------------------------|
|Ver el historial de comandos| `history`|
|Ver de cierto comando| `history | grep "comando"`|
|Limpiar el historial de comandos| `history -c`|

#### Limpiar la terminal

|                |Comando                          |
|----------------|-------------------------------|
|Limpiar la terminal| `clear` `CTRL + L`|
|Salir de la terminal| `exit`|

#### Ver la ruta actual

|                |Comando                          |
|----------------|-------------------------------|
|Ver la ruta actual| `pwd`|

## **Git init**

|                |Comando                          |
|----------------|-------------------------------|
|Inicializar repositorio|`git init`|

## **Status**

|                |Comando                          |
|----------------|-------------------------------|
|Verificar cambios|`git status`|
|archivos con cambios|`git status -s`|
|con cambios y rama actual|`git status -s -b`|

## **Add**: Agregar

|                |Comando                          |
|----------------|-------------------------------|
|todo|`git add .`|
|todo lo q se modificó|`git add -A`|
| cierta extensión|`git add *.png`|
|Con C_E de **TODO** el proyecto|`git add "*.png"`|
|todo|`git add --al`|
|en carpeta con cierta extensión|`git add pdfs/*.pdf`|
Se recomienda usar la interfaz de VSCode para agregar archivos al **stage**.

## **Commit**: guardar

|                |Comando                          |
|----------------|-------------------------------|
|Guardar con mensaje |`git commit -m "Mensaje"`|
|State y commit |`git commit -am "Mensaje"`|
|Modificar sms de commit (sin/con push)|`git commit --amend -m "Mensaje correcto"`|
|Volver al ultimo commit|`git checkout -- .`|
|eliminando todo hasta ese commit|`git reset --hard HEAD😍`|

Commits específicos, pa  **checkouts** sin afectar secciones de código bien hechas.

## **Reset**

|                |Comando                          |
|----------------|-------------------------------|
|Quitar del stage todos los archivos|`git reset .`|
|con cierta extensión|`git reset *.xml`|
|archivo en específico|`git reset HEAD "archivo"`|
|Quitar del STAGE archivo que tenía commit sin eliminar nada|`git reset --soft "HEAD^ o el id obtenido con"` `git lg`|
|Back to commit sin **quitar** cambios de los archivos|`git reset --mixed "id"`|
|Back to commit, pone todo como estaba ahí😎|`git reset --hard "id"`|

## **Reflog**: recuperar cambios después de un `git reset`

|                |Comando                          |
|----------------|-------------------------------|
|Mostrar historial (commits, **resets**, etc)|`git reflog`|
|Recuperar cambios😎: **reset (..hard)**, con id d **git reflog**|`git reset --hard "id_commit"`|

## **Log**: historial de commits

|                |Comando                          |
|----------------|-------------------------------|
|Ver commits|`git log`|
|hash (id) corto|`git log --oneline`|
|bonito|`git log --oneline --decorate --all --graph`|

## **DIFF** Revisar cambios

|                |Comando                          |
|----------------|-------------------------------|
|Ver cambios en  archivos|`git diff`|
|incluso estando en el stage|`git diff --staged`|

## Checkout

**Checkout**: es un comando que nos permite regresar a un commit anterior, pero sin perder los cambios que se han hecho en los archivos.
**¿Cómo funciona?**

1. Se hace un checkout al commit anterior
2. Se hace un commit con los cambios que se han hecho en los archivos

|                |Comando                          |
|----------------|-------------------------------|
|Ir al último commit|`git checkout -- .`|
|Ir '-', cierto archivo|`git checkout -- "archivo"`|

# Config de archivos desde Git

## Desde la terminal

|                |Comando                          |
|----------------|-------------------------------|
|Renombrar archivos|`git mv name.txt name2.txt`|
|Eliminar archivos|`git rm name.txt`|

Después de realizar estos comandos se deben hacer los **commits** para guardar los cambios, por que **ya estan** en el **STAGE** 😎.

## Desde el editor

Se renombra/eliminar en VSCode, al hacer `git status` Git dirá que eliminamos un archivo y hemos creado otro, para corregir esto y que Git sepa que es una actualización en el nombre debemos hacer lo siguiente:

|                |Comando                          |
|----------------|-------------------------------|
|Actualizar todo|`git add -u`|
|Agregar todo|`git add -A`|

Git reconoce que el archivo fue **renombrado**. Y podremos hacer el commit sin problemas.

## Ignorar archivos

Creamos archivo:  **.gitignore**

```sh
# Ignorar archivos con extensión .log, carpetas, pdf, imagenes, node, etc  :  *.log *.jpg *.jpeg *.gif *.mp4 *.mp3 *.zip *.rar *.7z *.tar
node_modules/
*.pdf
*.png
```

## **Crear** alias

|                |Comando                          |Ejemplo|
|----------------|-------------------------------|-------------------------------|
|Crear alias|`git config --global alias."alias" "codigo"`|`git config --global alias.lg "log --oneline --decorate --all --graph"`|
|Otro ejemplo|`git config --global alias."alias" "codigo"`|`git config --global alias.s "status -s -b"`|
|Ver datos globales y alias|`git config --global -l`|Sin ejemplo|
|Alias fer py 😎|git branch|`alias gb="git branch"`|
|Alias fer 😎|venv|`alias venv="source venv/Scripts/activate"`|

## **Alias** del fer⚽😎

```sh
    alias g='git'
    alias ga='git add --all'
    alias gb='git branch'
    alias gc='git commit  -m'
    # alias gca='git commit  -m'
    alias gco='git checkout'
    alias gs='git status -sb'
    alias gp='git push'
    alias gpl='git pull'
    # alias gca='git commit --amend'
    alias gca='git commit --amend -m'

    alias gcl='git clone'
    alias gcm='git checkout main'
    alias gcb='git checkout -b'
    alias gsh='git show'
     

  
    alias ll='ls -l'
    alias ls='ls -F --color=auto --show-control-chars'
```

Como configurar eso de manera global ?

1. Crear archivo:  **.bashrc**
2. Agregar alias
3. Guardar archivo

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
|Crear rama/moverse ahi con1 comando 😎|`git checkout -b nombre-rama`|
|Ver ramas|`git branch`|
|Ver ramas con commits|`git branch -v`|
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
|⚽🐱‍👤😎Crear/subir rama remota a github|`git push origin nombre-rama`|
|⚽🐱‍👤😎Subir rama remota a github|`git push (error cp en la rama)`|
|**Eliminar** rama remota|`git push origin :nombre-rama`|
|**Eliminar** rama eliminado en github remote|`git remote prune origin`|

## Ramas remotas con pull

|                |Comando                          |
|----------------|-------------------------------|
|Ver acceso remoto |`git remote -v`|
|Ver ramas remotas y locales y HEAD|`git branch -avvv`|
|Crear rama remota😍|`git pull origin nombre-rama`|
|Traer cambios de repositorio remoto|`git pull`|
|Con todas las ramas😎|`git pull --all`|
|**Y tags 👨‍🎓👿**|`git pull --all --tags`|

## Ramas remotas con fetch

|                |Comando                          |
|----------------|-------------------------------|
|Traer cambios de repositorio remoto|`git fetch`|
|con todas las ramas|`git fetch --all`|
|con todas las ramas y tags|`git fetch --all --tags`|

# Merge

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

```sh
    (<<<<<<<<<<<HEAD, ============, 
    >>>>>>>>>>>>>>)
```

y hacemos el commit.

# Tags

Son una referencia a un commit específico, se usan para guardar releases, usualmente se guardan usando número de versiones.
Se pueden descargar de GitHub.
|                |Comando                          |
|----------------|-------------------------------|
|Crear tags|`git tag name_v_tag`|
|Crear tags con versión y mensaje|`git tag -a v1.0.0 -m "mensaje"`|
|Crear tag en commit anterior|`git tag -a v0.1.0 hash-commit -m "mensaje"`|
|Ver tags (muestra versión_nombre que le dimos)|`git tag`|
|Borrar tags|`git tag -d name_tag`|
|Ver + detalle del tag|`git show name_tag`|
|Ver mensaje y demas de tags|`git show v1.0.0`|
|Subir tags a repositorio remoto|`git push origin --tags`|
|👿**Subir** tags a repositorio remoto|`git push --tags`|

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

# Rebase

**rebase**: es una forma de unir ramas, se usa cuando se quiere que la rama que se va a unir tenga los commits de la rama a la que se va a unir, es decir, que la rama que se va a unir sea la principal.

|                |Comando                          |
|----------------|-------------------------------|
|Rebase|`git rebase nombre-rama`|
luego del rebase se realiza el: `git merge rama y luego borrar la rama: git branch -d nombre_rama`
|                |Comando                          |
|----------------|-------------------------------|
|Rebase con squash: unir commit|`git rebase -i HEAD~4`|

## Comands

primero solo se edita la abreviatura luego: a+ esc + :  wq! enter
luego se edita en el otro panel 😀

- **r, reword:** edita el commit, el mensaje.
- **s, squash:** unir commit
- **f, fixup:** unir commit.
- **d, drop:** eliminar commit
- **p, pick:** conservar commit
- **e, edit:** para dividir commits. `git rebase --continue`
