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
