### Chuleta de control de versiones con git
## 1. Conceptos mínimos que tenemos que saber sobre el control de versiones

* **Control de versiones**: El control de versiones es un sistema que registra los cambios realizados sobre un archivo o conjunto de archivos a lo largo del tiempo, de modo que puedas recuperar versiones específicas más adelante

* **Conceptos:**
    *  **Repositorio local**: Es una base de datos centralizado donde se guardan las distintas versiones de los ficheros sometidos a control de versiones.

    * **Copia local**: (working copy) Es la copia que hacen los usuarios de un fichero sometido a control de versiones. El **DIRECTORIO LOCAL (working directory/working tree/workspace)** es el que contiene todas las copias locales. 

    * **Repositorio remoto**: (Remote repository/Repository)Es una base de datos centralizada donde se guardan las distintas versiones de los ficheros sometidos a control de versiones, y reside en el servidor centralizado. 

    * **Histórico**: (LOG)  Registro de todos los cambios que se han producido en el repositorio. Es responsabilidad del cliente añadir información al log cuando se produce un cambio. También llamado histórico.

    * **Conflicto**: Problema que surge cuando los clientes realizan cambios incompatibles entre sí.
    
* **Estados del fichero**:
	* **Sin seguimiento**: archivos que solo son locales y no existen en el repositorio remoto.

    * **Confirmado(commited file)**: Es el fichero que ya está almacenado en el repositorio. La última versión y la copia local son iguales.

    * **Modificado(modified file)**: Es el fichero modificado en la copia local y existe una diferencia entre la copia local y la última versión en el repositorio. 

    * **Preparado**: (staged file)Es la copia del fichero modificado preparada para ser confirmada en la próxima operación de confirmación (COMMIT). La zona de preparación (staging area or index) contiene todos los ficheros preparados.

    * **Ignorado(ignored file)**: Es el fichero que está en el directorio local pero que deliberadamente no se somete a control de versiones. 

* **Operaciones**:
    * **Clone**: (Clonar) Realiza una copia de un repositorio remoto en un directorio local.
    
    * **Add**: (Añadir) Realiza una copia de un fichero modificado, poniéndola en la zona de preparación para poder ser confirmada.
    
    * **Commit**: (Confirmar) Confirma los cambios en el repositorio local.
    
    * **Push**: (Enviar) Envía al repositorio remoto los cambios correspondientes a los commits realizados desde el último push.
    
    * **Pull**: (Traer) Descarga desde el repositorio remoto los archivos actualizados en commits que hayan realizado otros usuarios, y los integra (realiza un merge) con el repositorio local.
    
    * **Fork**: (Duplicado): Crear una copia de un repositorio. Esto es especialmente útil para modificar proyectos sin afectar al proyecto original.
    
    * **Pull Request**: (entre repositorios) Petición que hace el desarrollador de que los cambios hechos en su repositorio clonado mediante un FORK sean incorporados al repositorio original.
    
* **Servicios de repositorio remoto**: GitHub, GitLab, BitBucket, etc.

* **Clientes gráficos para el control de versiones**: gitg, gitkraken, gitblade, sourcetree, etc.

## 2. Que tenemos que saber hacer con Git (y GitHub)


### 2.1. Interprete de comando de git-bash
Comando    | Argumentos              | Función 
-----------|-------------------------|------------
**pwd**    |                         | Muestra el directorio actual (Print Working Directory).
**mkdir**  | &lt;dir>  ó  {nombre directorio}            | Crea un directorio.
**cd**     | &lt;dir>  ó  {nombre directorio}           | Cambia de directorio (*'cd -': directorio previo*).
**ls**     | [-l] [-a]               | Muestra los archivos del directorio *(l: detallado; a: incluye ficheros ocultos).*
**rm**     | &lt;file> ó  {file}            | Elimina un fichero.
**mv**     | &lt;source> &lt;dest> ó {origen} {destination}  | Mueve o renombra un archivo.

### 2.2. Control de versiones local

Comando        		 | Argumentos         | Función 
---------------------|--------------------|------------
**git init**   		 |     { nombre_repositorio}             | Crea un repositorio local en el directorio actual.
**git add**    		 | &lt;file>  ó  {nombre archivo}      | Prepara ficheros para ser confirmados en un repositorio local.
**git commit** 		 | [-m &lt;message>] ó -m "Descripción cambios"  | Confirma cambios en un repositorio local. *(m: permite escribir el mensaje del commit sin abrir el editor de texto).*	
**git commit**		|-am "Descripción cambios" | Add y commit en un solo paso
**git reset**  		 | &lt;file> ó {archivo}	  | Deshacer la operacion de preparar.
**git reset**  		 | [--soft]  ó  {commit}     | Deshace el add. *(soft: deshace el commit)*
**git status** 		 |					  | Identificar el estado de un fichero o ficheros en un repositorio local.
**git checkout**	 | <file>   ó {archivo}		  | Descartar los cambios de un fichero de trabajo mediante la recuperación de una versión almacenada en el repositorio local. 
**git checkout**     | &lt;branch_name>  ó {nombre_de_rama} | Cambia de rama en el repositorio local.
**git checkout**	| -b {nombre_de_la_rama}	| Crear una rama y cambiar a ella
**git branch**	| {nombre_de_tu_nueva_rama}	|Crear una rama en un repositorio local.
**git diff**   		 | &lt;file>          | Muestra los cambios de un archivo "modificado" con respecto al que hay en el repositorio.
