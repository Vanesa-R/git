# Mis comandos esenciales para utilizar Git

### Creando un repositorio local. Primeros pasos.

* **git init:** Inicia un repositorio.

* **git status:** Para conocer el estado de nuestros archivos. Podemos tener archivos en el área de trabajo, área de preparación y área de aprobación.

* **git add:** Para añadir archivos al área de preparación.

* **git commit:** Para aprobar cambios añadidos previamente al área de preparación.

* **git rm:** Para eliminar archivos. (git rm nombre_fichero)

* **git mv:** Para renombrar archivos. (git mv nombre_anterior nombre_nuevo)

* **git diff:** Muestra las diferencias que existen cuando se hacen cambios en un archivo. Compara los cambios de un archivo que ha sido aprobado (commit) y ahora tiene cambios en el área de trabajo). 
Muy importante: si hacemos cambios en un archivo, y después lo llevamos al área de preparación (add), al lanzar este comando no nos indicará si tiene diferencias con el archivo que se encuentra en el área de aprobación.

* **git diff --staged:** Compara los cambios de un archivo entre el área de trabajo y el área de preparación (add).

* **git diff --cached:** Compara los cambios de un archivo en el área de preparación (add) y el último commit.

* **git log --oneline:** Te muestra las revisiones que se han realizado con su ID.

* **git log --pretty=format:"%h %n %ar - %s":** Muestra las revisiones con el ID, junto al nombre de quien realizó el commit, cuándo lo realizó y el mensaje del commit.

* **git show (ID_revisión):** Muestra los ficheros que había en ese momento en el área de aprobación que indicamos en el ID.


### Trabajando con un repositorio remoto

* **git remote add origin dirección_repositorio:** Nos vinculamos al repositorio remoto.

* **git fetch origin:** Recupera todo lo que haya en origin (del repositorio remoto). Te muestra las ramas existentes (por convención la rama principal es master).

* **git pull origin master:** Descarga en tu repositorio local (rama master) el repositorio con el que nos hemos vinculado (origin).

* **git clone dirección_repositorio:** realiza a la vez git init, git fetch y git pull.

* **git push:** Enviar al repositorio remoto los cambios aprobados en el repositorio local.

* **git checkout --:** Con los guiones indicamos que lo que queremos que nos recupere son archivos.
* **git checkout HEAD -- .** : Recupera todos los archivos que hubiera en la última revisión.
* **git checkout HEAD~1 -- nombre_archivo:** Recupera el archivo de la penúltima revisión.

* **git reset --hard:** Es un comando muy agresivo. Realiza al mismo tiempo el git checkout y borra todo lo que está en el área de preparación.
* **git reset --hard HEAD~1:** Si tenemos en el área de preparación ficheros, eliminará su modificación. Además, eliminará los cambios que tuvieramos en los archivos en el área de la penúltima revisión

* **git revert:** Revierte cambios. Por ejemplo si ponemos git revert (ID_commit) lo que hará será eliminar los cambios aprobados en dicha revisión.
git revert (ID_commit)--no-edit: Añadiendo --no-edit logramos que no nos aparezca la ventana para dejar un mensaje del motivo por el que queremos revertir cambios.



### Trabajando con ramas

* **git branch nombre_nueva_rama rama_de_partida:** Con esto añadimos una nueva rama. Por ejemplo git branch new_rama master creará una nueva rama llamada new_rama

* **git checkout nombre_rama:** Con este comando podemos movernos entre ramas.

* **git branch -d nombre_rama:** Para eliminar una rama.

* **git branch -a:** Nos muestra todas nuestras ramas tanto en el repositorio local como el repositorio remoto.

* **git checkout -b nombre_nueva rama:** Crea una nueva rama y además nos posiciona en ella.



