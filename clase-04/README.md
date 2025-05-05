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
