# Clase 04 - Git Desarrollo Colaborativo

## GIT STASH

Estructura de datos tipo pila. Auxiliar para guardar temporalmente cambios que todavía no considero que puedo hacer un commit. No se pueden subir los stashes al remoto. Los Stashes son locales.

### Listar stashes

```sh
git stash list
```
## Crear un stash

```sh
git stash 
git stash -m "Describo que guarado dentro de este stash"
```

## Recuperar el último stash

```sh
git stash pop # Si no hay conflicto, lo borra el stash.
```

## Recuperar cualquier stash de los stashes

```sh
git stash apply <n>
git stash apply 2
git stash apply stash@{2}
```

## Borrar un stash

```sh
git stash drop # Borra el último elemento ingresado
git stash drop 1
git stash drop stash@{1}
```

## Alias de git
Una forma resumida de ejecutar un comando con varios opciones

### Crear Alias

```sh
git config --global alias.s "status -s"
git config --global alias.ll "log --oneline --decorate --graph --all"
```

### Listar Alias

```sh
git config --global --get-regexp alias
```

### Usar un alias

```sh
git s 
git ll
```

## Eliminar un alias

```sh
git config --global --unset alias.<alias-que-quiero-eliminar>
git config --global --unset alias.s
```

## GIT RESET

### git reset --soft
Borra el commit o los commit selecionados y coloca su contenido (del commit) en el staging area (index)

```sh
git reset --soft <hash>
```

### git reset --mixed (default)
Borrar el commit o lo commit selecionados y coloca el contenido (de/los commits) en el working directory

```sh
git reset --mixed <hash>
git reset <hash>
```

### git reset --hard
Borrar el commit o los commits selecionados y descarta su comentido.

```sh
git reset --hard <hash> # Con cuidado!
```

## Gist
Compartir código, pasar snippet a otras personas o información que quiero compartir. Pueden tener varios archivos y sus revisiones

<https://gist.github.com/>

* SECRETOS -> Solo la persona que tenga el link va a poder verlo. No son privados. 
* PÚBLICOS -> Se van indexar en los motores de búsqueda

## Proyectos
Son tableros visuales tipo Kanban donde podemos organizar y visualizar el progreso de nuestras tareas asociar tareas a resolución de issues.

## Issues (Posibles problemas, solución de temas)
Nos permiten tener un seguimiento sobre posibles bugs o errores en nuestras aplicaciones.

## Git Blame
Me va a permitir ver línea por línea quien fue el último que modificó esa línea y en que commit se hizo el cambio.

```sh
git blame <nombre-archivo>
git blame <nombre-archivo> -L # rango de líneas
git blame <nombre-archivo> -e o -s # correo o nombre del que hizo el commit
```

```sh
git blame --help
```

## Git Cherry Pick
Permite selecionar un commit o varios de manera independiente y colocarlos en otra rama.

## Selecciono un único commit 

```sh
git cherry-pick <hash>
```

### Seleciono varios commits con extremos

```sh
git cherry-pick <hash>^..<hash>
```

### Seleciono varios commits sin extremos

```sh
git cherry-pick <hash>..<hash>
```

### Para avanzar en la solución si hay conflicto
Si hay conflicto, solucionarlo y hacer los siguientes pasos

```sh
git add .
```

```sh
git cherry-pick --continue
```

### Git Restore para restablecer un archivo a un momento anterior

```sh
git restore --source <hash> <ruta-al-archivo>
git restore --source db9bbe5 clase-04/README.md
```

# GIT REVERT
Me permite deshacer un commit y crear uno nuevo con una versión anterior del archivo/s

## Revierte un commit en particular

```sh
git revert <hash>
```

## Revierte un rango de commit en particular

```sh
git revert <hash>..<hash>
```

## Revierte un commit pero no hace el commit del revert...

```sh
git revert --no-commit <hash>
```

## Trabajar colaborativamente con personas que no conozco (Fork y Pull Request)

Me permite trabajar colaborativamente en proyectos donde no conozco a las personas o no tengo la suficiente confianza para darle permisos al repositorio de trabajo. 

Normalmente cuando trabajo con Fork y Pull Request lo hago en proyectos Open Source.

* Fork es una copia del respositorio remoto de alguien a mi cuenta de GitHub.
* Pull Request. Solicitud  a los dueños originales del repositorio para proponerles un cambio. Es una propuesta de cambio a alguien que no conozco pero quiero ayudar.

1. Hacer un fork del proyecto. Del proyecto del cual quiero contribuir (Me voy copiar en mi cuenta el repo del proyecto original)
2. Me clono el fork desde mi cuenta github
3. Trabajo normalmente. Subo los cambios (A repo propio)
4. Me voy al proyecto original en el apartado Pull Request. Creo un nuevo Pull Request. Algunas veces aparece en mi repo la posibilidad Pull Request.
---
5. Si el repo original sufrió más modificaciones. (Commits). Voy a tener que actualizar mi fork.
6. Voy a la cuenta del proyecto original y me copio la url del repositorio
7. Y agrego en mi repositorio local, la url (el remoto) del proyecto original.

    git remote add upstream <URL-repositorio-original>

8. Me traigo los cambios del repositorio original a mi repo local

    git pull upstream <rama-que-quiero-actualizar>

9. Subo a mi repositorio remoto (Fork) las actualizaciones del repo local

    git push origin <rama-a-actualizar>
