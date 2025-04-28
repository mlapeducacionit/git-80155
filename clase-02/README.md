# Clase 02 - Git desarrollo Colaborativo

## git remote (configurar la ruta del repositorio remoto)

### Agregar un remoto

```sh
git remote <comando> <alias> <url>
git remote add origin <https://github.com/mlapeducacionit/git-80155.git>
```

### Borrar un remoto

```sh
git remote remove <alias>
git remote remove origin
```

### Listar los remotos

```sh
git remote 
git remote -v #detalle (v -> verbose)
```

# git push (Subir cambios del repo local al repo remoto)

```sh
git push <remoto> <local>
git push origin main # Si existe la rama main en el remoto sube los cambios y si no existe crea la rama main en el remoto y sube los cambios

git push -u origin main # La primera vez que subo una rama al repositorio remoto
# -u -> Es sincronizar la rama del remoto con la rama del local -> Vincular la rama local con la rama remota.

git push # Las sucesivas veces que haga git push, no necesito indicar el remoto y la rama que quiero subir
```

# git fetch
Me actualiza la carpeta .git (Me actualizar la carpeta .git del local con respecto al remoto)

```sh
git fetch
git fetch --help
```

# git pull
Me traigo (archivos/carpetas) los cambios que están en el remoto al local

```sh
git pull <remoto> <rama>
git pull origin main
```

## Listar ramas locales y remotas

```sh
git branch -av # -a -> all | -v -> verbose
```

## Listar commits de todas las ramas disponibles, tanto locales como remotas

```sh
git log --oneline --all
```

# Ramas (Branches)

## Listar ramas

```sh
git branch
```

## Para crear una rama

```sh 
git branch <nombre-rama>
git branch dev
```

## Para cambiar de rama

```sh
git switch <nombre-rama>
git switch dev
```

## Para crear una rama y cambiarme a esa rama

```sh
git switch -c <nombre-rama>
git switch -c hotfix
```

## Si quiero volver a la última rama en la que estuve

```sh
git switch -
```
