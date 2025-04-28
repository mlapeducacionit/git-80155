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