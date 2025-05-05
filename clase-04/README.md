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