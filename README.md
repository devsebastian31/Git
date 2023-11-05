# Curso de Git

<p align="center">
<img src="Logotipo.png" width="500ppx">
</p>

Git es un sistema de control de versiones muy utilizado que permite gestionar el historial de cambios en proyectos de software. A continuación, te proporciono una lista de algunos comandos de Git y una breve descripción de para qué sirve cada uno. Ten en cuenta que Git tiene muchos comandos y opciones, por lo que esta lista es solo una introducción:

1. `git init`: Inicia un nuevo repositorio Git en un directorio vacío o existente.

2. `git clone`: Clona un repositorio Git desde una ubicación remota a tu sistema local.

3. `git add`: Agrega cambios en los archivos al área de preparación (staging).

4. `git commit`: Crea un nuevo commit con los cambios en el área de preparación.

5. `git status`: Muestra el estado actual de los archivos en el repositorio.

6. `git log`: Muestra el historial de commits.

7. `git diff`: Muestra las diferencias entre cambios en el área de trabajo y el área de preparación.

8. `git branch`: Lista las ramas en el repositorio.

9. `git checkout`: Cambia a una rama específica o un commit.

10. `git merge`: Combina los cambios de una rama en otra.

11. `git pull`: Descarga cambios desde un repositorio remoto y los fusiona en la rama local.

12. `git push`: Sube los commits locales a un repositorio remoto.

13. `git remote`: Muestra las ubicaciones remotas configuradas.

14. `git fetch`: Descarga información sobre cambios desde un repositorio remoto, pero no fusiona los cambios.

15. `git reset`: Permite deshacer cambios en el área de preparación o el último commit.

16. `git stash`: Guarda temporalmente cambios no comprometidos en una pila de cambios (stash).
s
17. `git tag`: Permite etiquetar commits para marcar versiones o puntos importantes en la historia.

Estos son algunos de los comandos más comunes de Git, pero hay muchos otros comandos y opciones disponibles para tareas más específicas. Puedes obtener más información sobre cada comando utilizando `git help <comando>` o `git <comando> --help`, o consultando la documentación oficial de Git en línea.

<br>

### Configuración de Usuarios

Configurar Nombre que salen en los commits
```ssh
	git config --global user.name "usuario"
```
Configurar Email
```ssh	
	git config --global user.email usuario@gmail.com
```

<br>

### Iniciar repositorio y subir a Github

Iniciamos GIT en la carpeta donde esta el proyecto
```ssh
	git init
```
Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Añadimos todos los archivos para el commit
```ssh
	git add .
```
Hacemos el primer commit
```ssh
	git commit -m "Version 1"
```
subimos al repositorio
```ssh
	git push origin master
```

<br>

### GIT CLONE


Clonamos el repositorio de github
```ssh
	git clone <url>
```

<br>

### GIT ADD


Añadimos todos los archivos para el commit
```ssh
	git add .
```
Añadimos el archivo para el commit
```ssh
	git add <archivo>
```
Añadimos todos los archivos para el commit omitiendo los nuevos
```ssh
	git add --all 
```
Añadimos todos los archivos con la extensión especificada
```ssh
	git add *.txt
```
Añadimos todos los archivos dentro de un directorio y de una extensión especifica
```ssh
	git add docs/*.txt
```
Añadimos todos los archivos dentro de un directorios
```ssh
	git add docs/
```

<br>

### GIT COMMIT

Cargar en el HEAD los cambios realizados
```ssh
	git commit -m "Version 1"
```
Agregar y Cargar en el HEAD los cambios realizados
```ssh
	git commit -a -m "Version 1"
```
De haber conflictos los muestra
```ssh
	git commit -a 
```
Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje
```ssh
	git commit --amend -m "Version 1"
```

<br>

### GIT PUSH

Subimos al repositorio
```ssh
	git push <origien> <branch>
```
Subimos un tag
```ssh
	git push --tags
```

<br>

### GIT LOG

Muestra los logs de los commits
```ssh
	git log
```
Muestras los cambios en los commits
```ssh
	git log --oneline --stat
```
Muestra graficos de los commits
```ssh
	git log --oneline --graph
```

<br>

### GIT DIFF

Muestra los cambios realizados a un archivo
```ssh
	git diff
	git diff --staged
```

<br>

### GIT REMOTE

Agregar repositorio remoto
```ssh
	git remote add origin <url>
```
Cambiar de remote
```ssh
	git remote set-url origin <url>
```
Remover repositorio
```ssh
	git remote rm <name/origin>
```
Muestra lista repositorios
```ssh
	git remote -v
```
Muestra los branches remotos
```ssh	
	git remote show origin
```
Limpiar todos los branches eliminados
```ssh
	git remote prune origin 
```

<br>

### GIT BRANCH

Crea un branch
```ssh
	git branch <nameBranch>
```
Lista los branches
```ssh
	git branch
```
Comando -d elimina el branch y lo une al master
```ssh
	git branch -d <nameBranch>
```
Elimina sin preguntar
```ssh
	git branch -D <nameBranch>
```

<br>

### GIT TAG

Muestra una lista de todos los tags
```ssh
	git tag
```
Crea un nuevo tags
```ssh
	git tag -a <verison> - m "Version 1"
```

<br>

### GIT REBASE

Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge
```ssh
	git rebase
```
Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
```ssh	
	git rebase --continue 
```
Omite el conflicto y sigue su camino
```ssh
	git rebase --skip
```
Devuelve todo al principio del rebase
```ssh
	git reabse --abort
```
Para hacer un rebase a un branch en especifico
```ssh	
	git rebase <nameBranch>
```

<br>

### OTROS COMANDOS

Lista un estado actual del repositorio con lista de archivos modificados o agregados
```ssh
	git status
```
Quita del HEAD un archivo y le pone el estado de no trabajado
```ssh
	git checkout -- <file>
```
Crea un branch en base a uno online
```ssh
	git checkout -b newlocalbranchname origin/branch-name
```
Busca los cambios nuevos y actualiza el repositorio
```ssh
	git pull origin <nameBranch>
```
Cambiar de branch
```ssh
	git checkout <nameBranch/tagname>
```
Une el branch actual con el especificado
```ssh
	git merge <nameBranch>
```
Verifica cambios en el repositorio online con el local
```ssh
	git fetch
```
Borrar un archivo del repositorio
```ssh
	git rm <archivo> 
```