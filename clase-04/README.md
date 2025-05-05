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