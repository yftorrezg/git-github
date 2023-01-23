# Apuntes

## comandos

al haber '--' se escribe la palabra completa.
``git --version``
Encambio si solo hay '-' indica la abreviacion. Ej:
``git commit -am``--> solo sirve si se le da seguimiento a los archivos
**CTRL + L**: limpia la terminal --> clear
**para salir de terminal** --> ``ESC :  Q  W  !`` enter

**Untrack** --> git no le da seguimiento
**Ctrl + shift + g  G** --> abre git(extencion) de VSCode
**-** : baja del stage
**+** : sube al stage
**git diff**: sin el stage 😀

## comandos de git

<!-- lista de comandos tabla -->

| comando | descripcion |
| ------- | ----------- |
| git config --global color.ui true | cambia el color |
| git config --global core.editor "nano" | cambia el editor |

| COMANDO | DESCRIPCION |
| ------- | ----------- |
|**git checkout .** | vuelve al commit anterior |
| git checkout -- nombre | vuelve al commit anterior del archivo |
| git checkout -b nombre | crea un branch y se cambia a el |
| git checkout nombre | cambia al branch |
| git merge --abort | aborta la fusion |
| git merge --continue | continua la fusion |

## cambiar nombre de master a main

git branch -m master main
<!-- cambiarlo como definitivo init.deffault -->
git config --global init.defaultBranch main
<!-- cambiarlo en el repositorio -->
git branch -M main
`git pull --all`: trae todas las ramas de github
`git branch -a`: nos muestra las ramas remotas q bajó
