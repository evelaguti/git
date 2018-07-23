# Glosario 

## GIT 

### Git fue creado por Linus Torvalds.

* Velocidad: Puedes trabajar fluidamente desde tu computador
* Diseño sencillo: El codigo es robusto con las herramientas necesarias, como viajar en el tiempo
* Fuerte apoyo en el desarrollo no lineal: No trabaja de manera linea, la linea del tiempo tiene bifurcaciones de manera independiente al proyecto principal
- Completamente distribuido: Cada quien puede tener una copia del proyecto.
- Capaz de manejar grandes proyectos: Linux, Django, Laravel, etc. Usan git
- Git almacena referencias a los archivos que no se han cambiado.
- Cualquier trabajo es local, puedes trabajar en cualquier parte incluso sin internet.
 

### Tipos
 - Local: Vive en nuestro computador. Si le ocurre una catástrofe vamos a perder nuestro trabajo, además de que Ctrl + Z tiene cierta limitación
 - Centralizado: Depende de un super server donde está almacenado el repositorio. Si se quema el super server vamos a llorar y perdemos nuestro trabajo.
 - Distribuido: Cada participante del repositorio tiene una copia local y no afecta el trabajo del resto. No perdemos nuestro trabajo si nuestro se computador se daña, simplemente pedimos una copia a cualquier servidor donde esté almacenada la copia

### Etapas

- **Working Directory**: Es donde trabajamos de manera local, pero para guardarlo hay que pasarlo al Staging Area
- **Staging Area**: Es el área de preparación, se almacenan justo antes de hacer commit
- **Local Repository**: El repositorio local donde almacenaremos los cambios del proyecto
- **Repository**: El repositorio en el servidor donde almacenaremos los cambios del proyecto


### Comandos Terminal

- **cd**  Change directory
- **mkdir**  Make directory
- **ls**  list - en ++windows ++deben usar dir
- **ls -a** nos muestra los archivos o carpetas ocultas en la terminal
- **clear** también se puede usar control + L
- **touch** crea un archivo o modifica su fecha de modificación.
- **rm** remove -rf(para borrar carpetas)
- 
- **Nunca usar rm -rf / o se despiden de su pc 😞**

### VIM
- **i** = para poder editar
- **:wq** = para guardar y salir
- **:q!** = para salir sin guardar

### Comandos Git
- **git init** : Crea un repositorio de manera local y lo hará en la carpeta donde estamos posicionados o se le puede pasar [nombre_de_la_carpeta] y creará la carpeta con ese nombre.
- **git status**: Muestra el estado del repositorio local.
- **git add [archivo]**: Agrega el archivo al staging area **-A** nos agrega todos los archivos.
- **git rm --cached [archivo]**: Sacamos el archivo del staging area.
- **git rm -f [archivo]**: Remueve el archivo de staging y tambien del working directory.
- **git add -n [archivo]**: No agrega el archivo a staging area sólo muestra que existe ó es ignorado.
- **git commit -m "mensaje"**: Envía los archivos que se encuentran en 'Staging Area' a 'Local Repository' Es bueno ser descriptivos con el mensaje para saber lo que se hizo en ese commit y para informar al resto de personas.
- **git commit -–amend**: concatena nuevos cambios con cambios previos.   

git log: nos muestra la historia de todos los commits que hemos realizados.

#### Untracked files
 Son archivos que están en nuestro Working Directory, lo que aparezca en rojo es lo que se ha modificado y hay que pasarlo al Staging.



