# Clase 01 - Git Desarrollo Colaborativo

## Verificando que tenga git instalando

```sh
git --version
```

## Ver si tengo un usuario y correo configurado

```sh
git config --global -e
# Controla especificamente si tengo usuario y correo
git config --global --get-regexp user
```

## Configuración inicial

```sh
git config --global user.name "Maximiliano Principe"
git config --global user.email mlapeducacionit@gmail.com
```

## Como remover algo que no deseo este

```sh
git config --global --unset user.email
```

## Cambiar el editor a nano

```sh
git config --global core.editor nano
```

# Creando el repositorio de git
Eso crea la carpeta .git que es la metadata del repositorio

```sh
git init
```

## Listar archivos directorio actual

```sh
ls # listar
```

## Cambiar el nombre por defecto de la rama principal

```sh
git config --global init-defaultBranch main
```

## Estados de los archivos en un repositorio de GIT

* Untracked (Sin seguimiento) => archivos que no se agregaron al index/stage y por consecuente no se les da seguimiento.
* Staged => Archivos que fueron agregados al index/stage area y cuyos cambios van a ser incorporados al repositorio
* Unmodified => Archivos que se cuentran en en el respositorio y no fueron modificado (Con respecto al repositorio)
* Modified => Archivos que se encuentro en el repositorio pero difieren con lo que se encuentra actualmente en el directorio trabajo (Working directory)

## Areas posibles en las que pueden estar los archivos

* Working Directory (Directorio de trabajo) donde se van agregando y borrando archivos en desarrolllos

* Staging Area (Area de control de cambios) Se agregan los archivos para darle seguimiento y posteriormente sacarles una foto (commit)

* Local Repo (Area de validación de cambios, donde se registran las modificaciones realizadas) Donde van a estar todas las fotos (commit) que vaya sacando.

## Agrego en el staging area archivo (Area de confirmación)

```sh
git add <nombre-archivo>
git add clase-01/README.md
```

## Hacer un commit de los cambios que están en el Staging Area

```sh
git commit -m "Mensaje descriptivo"
```

## Ver las diferencias entre los archivos que están en el Working Directory contra el Local Repo

```sh
git diff
```

## Listar timeline de commits dentro del repo local

```sh
git log
git log --oneline
```

## Para recuperar archivos que están dentro del local repo

```sh
git restore <nombre-archivo>
git restore clase-01/README.md
git restore . # todos los archivos
```
