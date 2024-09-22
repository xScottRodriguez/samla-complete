


## Dev

1. clonar el repo
2. actualizar las referencias en los submodulos: `git submodule update --init --recursive`
3.  crear `.env` basado en el `.env.template`
4. Ejecutar comando: `docker compose up --build`

# Dato importante
Si cambias de rama en `samla-complete`, deberas cambiar de rama los submodulos en caso trabajes en uno de los submodulos, si el cambio de rama solo modifica el `samla-complete` no habria problema.



### Pasos para crear los Git Submodules
1. Crear un nuevo repositorio en GitHub
2. Clonar el repositorio en la máquina local

3. Añadir el submodule, donde `repository_url` es la url del repositorio y `directory_name` es el nombre de la carpeta donde quieres que se guarde el sub-módulo (no debe de existir en el proyecto)
```
git submodule add <repository_url> <directory_name>
```
4. Añadir los cambios al repositorio (git add, git commit, git push)
Ej:
```
git add .
git commit -m "Add submodule"
git push
```
5. Inicializar y actualizar Sub-módulos, cuando alguien clona el repositorio por primera vez, debe de ejecutar el siguiente comando para inicializar y actualizar los sub-módulos
```
git submodule update --init --recursive
```
6. Para actualizar las referencias de los sub-módulos
```
git submodule update --remote

```

## Pasos para Trabajar con el samla-complete


## Importante
Si se trabaja en el repositorio que tiene los sub-módulos, **primero actualizar y hacer push** en el sub-módulo y **después** en el repositorio principal. 

Si se hace al revés, se perderán las referencias de los sub-módulos en el repositorio principal y tendremos que resolver conflictos.

 si trabajas dentro de algun servicio, tene en cuenta que no debes hacer ningun commit ni push cuando en los cambios del git diff veas a la par del hash del commit un dirty esto podria generar conflictos en el codigo.
 Deberas hacer el siguiente procedimiento para evitar esto:
 si modificas un submodule, primero haz commit en el submodule y luego push de los cambios,
 luego hace commit en el samla-complete y luego haz push, esto mantendra actualizado las referencias en los submodulos.



