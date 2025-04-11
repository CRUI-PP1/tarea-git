# Actividad: Introducción a Git

**Prerrequisitos:**
* Tener Git instalado en su sistema. Puede verificar la instalación abriendo una consola (CMD, PowerShell o Git Bash) y ejecutando: `git --version`.
* Poseer conocimientos básicos sobre el manejo de la consola o el Explorador de Archivos de Windows para la creación/gestión de carpetas y archivos de texto.

---

## Ejercicio 1: Crear y trackear un archivo

1.  **Cree un archivo:**
    * Dentro de la carpeta en donde se clonado el repositorio, cree un archivo de texto simple denominado `primer_archivo.txt`. Puede utilizar el Bloc de notas u otro editor de texto, o crearlo mediante clic derecho -> Nuevo -> Documento de texto y renombrándolo (asegúrese de que la extensión sea `.txt`).
    * Ábralo con un editor e ingrese el siguiente contenido:
        ```
        Mi Primer Repositorio
        ```
    * Guarde los cambios y cierre el archivo.

2.  **Verifique el estado nuevamente:**
    * Ejecute `git status` en la consola.
    * **Pregunta:** Tras la creación del archivo `primer_archivo.txt`, ¿cómo lo clasifica Git? ¿Qué significa que el archivo esté en la categoría "Untracked files"?

3.  **Agregue el archivo al Área de Preparación (Staging Area):**
    * Para indicar a Git que desea incluir este archivo en el próximo commit (confirmación de cambios), utilice el comando `git add`:
        ```bash
        git add primer_archivo.txt
        ```

4.  **Verifique el estado una vez más:**
    * Ejecute `git status`.
    * **Pregunta:** ¿En qué sección aparece ahora el archivo `primer_archivo.txt`? ¿Qué indica la sección "Changes to be committed"?

---

## Ejercicio 2: Realizar el primer commit

1.  **Confirme los cambios:**
    * Realice una confirmación de cambios en el repositorio. Guarde el estado actual en el historial del repositorio utilizando `git commit`. Es fundamental incluir un mensaje descriptivo utilizando la opción `-m`:
        ```bash
        git commit -m "Commit inicial: Agrega archivo primer_archivo.txt"
        ```
    * **Pregunta:** ¿Qué resumen de la operación muestra Git después de ejecutar `git commit`? ¿Proporciona detalles sobre los archivos afectados?

2.  **Verifique el estado final y el historial:**
    * Ejecute `git status`.
        * **Pregunta:** ¿Qué mensaje muestra `git status` después de realizar el commit? ¿Qué indica el estado "working tree clean"?
    * Para visualizar el historial de commits, ejecute `git log`:
        ```bash
        git log
        ```
        * **Pregunta:** ¿Qué información relevante puede observar acerca de su primer commit? (Para salir de la vista de `git log`, presione la tecla `q`).

---

## Ejercicio 3: Modificar un archivo y confirmar los Cambios

1.  **Modifique el archivo:**
    * Abra nuevamente el archivo `primer_archivo.txt` con su editor de texto.
    * Agregue una nueva línea al final del archivo con el texto: `Este es un proyecto de ejemplo para practicar Git.`
    * Guarde los cambios realizados.

2.  **Verifique el estado:**
    * Ejecute `git status`.
    * **Pregunta:** ¿Qué indica Git acerca del archivo `primer_archivo.txt` después de la modificación? ¿Qué significa el estado "Changes not staged for commit"?

3.  **Prepare los cambios para el commit:**
    * Es necesario agregar explícitamente las modificaciones al Staging Area para incluirlas en el próximo commit. Utilice `git add`:
        ```bash
        git add primer_archivo.txt
        ```

4.  **Verifique el estado nuevamente:**
    * Ejecute `git status`.
    * **Pregunta:** ¿En qué sección aparece ahora el archivo `primer_archivo.txt` modificado?

5.  **Confirme la modificación:**
    * Realice un nuevo commit con un mensaje descriptivo:
        ```bash
        git commit -m "Actualiza primer_archivo.txt con texto adicional"
        ```

6.  **Revise el historial actualizado:**
    * Utilice `git log --oneline` para una visualización compacta del historial.
    * **Pregunta:** ¿Cuántos commits se observan ahora en el historial? ¿Qué diferencia hay entre `git log` y `git log --oneline`? ¿Qué es `--oneline` al final del comando?

---

## Ejercicio 4: Crear y agregar un nuevo archivo

1.  **Cree un segundo archivo:**
    * En la carpeta del repositorio, cree un nuevo archivo de texto denominado `segundo_archivo.txt`.
    * Puede dejarlo vacío o agregar un texto simple como: `Este es mi segundo archivo`. Guarde el archivo.

2.  **Verifique el estado:**
    * Ejecute `git status`.
    * **Pregunta:** ¿Cómo clasifica Git al nuevo archivo `segundo_archivo.txt`? ¿Es similar a la clasificación inicial del archivo `primer_archivo.txt`?

3.  **Agregue y confirme el nuevo archivo:**
    * Realice los dos pasos necesarios: agregarlo al Staging Area y confirmar el commit.
        ```bash
        git add segundo_archivo.txt
        git commit -m "Agrega archivo segundo_archivo.txt"
        ```

4.  **Verificación final del estado y el historial:**
    * Ejecute `git status`.
        * **Pregunta:** ¿Qué indica `git status` sobre el estado actual del repositorio?
    * Ejecute `git log --oneline`.
        * **Pregunta:** ¿Cuántos commits figuran ahora en el historial?

---

## Ejercicio 5: Modificar múltiples archivos simultáneamente

1.  **Consigna:** Realice modificaciones en los dos archivos existentes (`primer_archivo.txt` y `segundo_archivo.txt`) antes de efectuar el siguiente commit.
    * Modifique `primer_archivo.txt`: Abra el archivo y agregue una nueva línea al final, por ejemplo: `Agregando más detalles al primer_archivo.txt` . Guarde los cambios.
    * Modifique `segundo_archivo.txt`: Abra el archivo y reemplace todo su contenido con: `Estoy reemplazando todo el contenido del archivo` . Guarde los cambios.

2.  **Verifique el estado:**
    * Ejecute `git status`.
    * **Pregunta:** ¿Qué archivos lista `git status` como modificados? ¿Indica de alguna forma que hay múltiples archivos con cambios?

3.  **Prepare ambos cambios:**
    * Agregue todos los cambios pendientes al Staging Area utilizando un punto (`.`):
        ```bash
        git add .
        ```
4.  **Verifique el estado nuevamente:**
    * Ejecute `git status`.
    * **Pregunta:** ¿Cómo aparecen listados ahora los archivos `primer_archivo.txt` y `segundo_archivo.txt`? ¿Se encuentran ambos preparados para ser incluidos en el mismo commit?
    * **Pregunta:** ¿Qué diferencia hay entre `git add <nombre_de_archivo>` y `git add .`?

5.  **Confirme los cambios combinados:**
    * Realice un commit que describa ambas modificaciones:
        ```bash
        git commit -m "Actualiza primer_archivo.txt y corrige segundo_archivo.txt"
        ```
6.  **Revise el historial:**
    * Ejecute `git log --oneline`.
    * **Pregunta:** ¿Se visualiza el nuevo commit que agrupa los cambios de ambos archivos? ¿Cuántos commits existen ahora en el historial?

---

## Ejercicio 6: Eliminar un archivo del repositorio

1.  **Consigna:** Elimine el archivo `segundo_archivo.txt` del proyecto utilizando las herramientas del sistema operativo y luego registre dicha eliminación en Git.
    * Primero, elimine el archivo `segundo_archivo.txt` de la carpeta del repositorio utilizando el método que prefiera (por ejemplo, seleccionándolo y presionando la tecla Suprimir en el Explorador de Archivos, o ejecutando `del segundo_archivo.txt` en la consola).

2.  **Verifique el estado después de la eliminación manual:**
    * Ejecute `git status` en la consola.
    * **Pregunta:** ¿Qué le muestra `git status` ahora? ¿Cómo indica que el archivo `segundo_archivo.txt` fue eliminado de su carpeta pero que ese cambio todavía no está preparado ("staged") para el commit?

3.  **Prepare ("Stage") la eliminación para el commit:**
    * Ahora, debe indicarle a Git que desea registrar esta eliminación en el próximo commit. Prepare ("stage") la eliminación utilizando `git add` sobre el nombre del archivo que eliminó manualmente:
        ```bash
        git add segundo_archivo.txt
        ```
    * *Nota:* Aunque parezca contraintuitivo usar `git add` sobre un archivo eliminado, este comando le indica a Git que prepare el estado actual del archivo (en este caso, su ausencia) para el próximo commit.

4.  **Verifique el estado después de preparar la eliminación:**
    * Ejecute `git status` nuevamente.
    * **Pregunta:** Observe la salida. ¿En qué sección aparece ahora la eliminación del archivo `segundo_archivo.txt`? ¿Indica que está listo para ser confirmado?

5.  **Confirme la eliminación:**
    * Realice un commit para registrar la eliminación del archivo en el historial:
        ```bash
        git commit -m "Elimina archivo segundo_archivo.txt"
        ```
6.  **Verifique el estado final y el directorio:**
    * Ejecute `git status`.
        * **Pregunta:** ¿Cuál es el estado actual del repositorio?
    * Revise el contenido de la carpeta del repositorio (con el Explorador de Archivos o el comando `dir` en la consola).
        * **Pregunta:** ¿Continúa existiendo el archivo `segundo_archivo.txt` en la carpeta?

---

## Ejercicio 7: Trabajar con directorios y archivos nuevos

1.  **Consigna:** Cree una nueva estructura de directorios y agregue archivos dentro de ella.
    * Dentro de la carpeta del repositorio, cree un nuevo directorio llamado `documentos`.
    * Ingrese al directorio `documentos` y cree dos archivos de texto:
        * Uno denominado `guia.txt`. Ingrese el texto: `Guía de uso básico.` y guárdelo.
        * Otro denominado `notas.txt`. Ingrese el texto: `Notas varias sobre el proyecto.` y guárdelo.

2.  **Verifique el estado:**
    * Regrese al directorio principal del repositorio en la consola si es necesario. Ejecute `git status`.
    * **Pregunta:** ¿Cómo muestra `git status` el nuevo directorio `documentos/` y su contenido? ¿Lo identifica como "Untracked"?

3.  **Prepare el directorio completo:**
    * Agregue todo el contenido del directorio `documentos` al Staging Area especificando el nombre del directorio:
        ```bash
        git add documentos/
        # También puede usar git add . si no existen otros cambios sin preparar.
        ```
4.  **Verifique el estado nuevamente:**
    * Ejecute `git status`.
    * **Pregunta:** ¿Cómo aparecen ahora los archivos `documentos/guia.txt` y `documentos/notas.txt`? ¿Indica que están listos para el commit?

5.  **Confirme los nuevos archivos y directorio:**
    * Realice el commit correspondiente:
        ```bash
        git commit -m "Agrega directorio 'documentos' con guía y notas iniciales"
        # Ojo al uso de las comillas simples y dobles.
        ```

---

## Ejercicio 8: Desafío - Operaciones combinadas

1.  **Consigna:** Realice las siguientes operaciones antes de ejecutar un único commit:
    * Modifique el archivo `primer_archivo.txt`: ábralo y agregue una nueva sección al final, por ejemplo:
        ```

        ## Sección de Desafío
        Combinando operaciones Git.
        ```
        Guarde los cambios.
    * Modifique un archivo dentro de `documentos`: abra `documentos/guia.txt` y agregue al final: `Actualización importante en la guía.` Guarde los cambios.
    * Cree un archivo nuevo en el directorio raíz del proyecto llamado `configuracion.txt` y escriba:
        ```
        configuracion importante del proyecto
        ```
        Guarde el archivo.
    * Elimine el archivo `documentos/notas.txt` utilizando su método de preferencia.

2.  **Verifique el estado:**
    * Ejecute `git status`.
    * **Pregunta:** Analice la salida. ¿Cuántos tipos diferentes de cambios detecta Git (modificados, nuevos, eliminados)? ¿Cómo los presenta en la salida?

3.  **Prepare todos los cambios:**
    * Agregue todos los cambios detectados (modificaciones, archivo nuevo, eliminación) al Staging Area:
        ```bash
        git add .
        ```
4.  **Verifique el estado nuevamente:**
    * Ejecute `git status`.
    * **Pregunta:** ¿Cómo se visualizan ahora todos los cambios? ¿Distingue Git entre los diferentes tipos de cambio (modificados, nuevos, eliminados) en esta sección?

5.  **Confirme el conjunto de cambios:**
    * Realice un único commit que agrupe todas estas operaciones, utilizando un mensaje descriptivo:
        ```bash
        git commit -m "Desafío: Modifica primer_archivo y guía, agrega configuracion, elimina notas"
        ```

6.  **Verificación final:**
    * Ejecute `git status`.
        * **Pregunta:** ¿Indica que el repositorio se encuentra limpio?
    * Ejecute `git log --oneline`.
        * **Pregunta:** ¿Puede identificar el último commit que agrupa todas las operaciones del desafío? ¿Cuántos commits existen en total en el historial?
