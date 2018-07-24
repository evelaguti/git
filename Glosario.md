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


### Glosario Terminal

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
- **git tag**: Nos permite agregar etiquetas a nuestros cambios.
- **-a** para la anotación
- **-m** para el mensaje
- **-l** nos muestra la lista de etiquetas
- **-f** para renombrar
- **-d** para borrar
- **git log**: Muestra la historia de todos los commits que hemos realizados.

#### Superlog
```
git config --global alias.superlog "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```

#### Untracked files
 Son archivos que están en nuestro Working Directory, lo que aparezca en rojo es lo que se ha modificado y hay que pasarlo al Staging.
#### Tipos de tag
- tag ligera
```
git tag 1.0 "SHA" 
git tag 1.0 02512454212dfd2s...
```
- tag anotada
```
git tag -a 1.0 -m 'version estable' 0251245421...
git tag -a "version" -m "mensaje" "SHA"
```

##### Opciones
- Borrar tags
```
git tag -d 1.0
git tag -d "versíon"
```
- Renombrar tags
```
git tag -f -a 0.1 'iniciando el proyecto' SHA
```
- Listar tags
```
git tag -l
```

###### Nota
Si no se coloca el sha al final del mensaje, el tag se colocorá al ultimo commit

#### Diff 
```
git diff [SHA1 o tag] // Nos muestra las cambios de ese commit.
``
- Rojo: fueron cambios que se quitaron
- Verde: se agregaron cosas
```

#### Reset
```
git reset --soft sha // elimina commits hasta exclusivo el commit indicado, dejando los archivos en el staging area.
git reset --mixed sha // elimina commits hasta excluvivo el commit indicado dejando los archivos en el working directory
git reset --hard sha // elimina commits hasta excluvivo el commit indicado borrando tambien los archivos del working directory

```
#### Ramas

Las ramas son muy importantes si quieres trabajar con un equipo y no quieres tocar la rama master para no crear conflictos,
```
git branch [nombre] se crea una nueva rama
git branch -l: listamos las ramas
git branch -d/-D [nombre]: borramos rama
git branch -m [nombre] [nombre_nuevo]: para renombrar ramas
```
#### Checkout
```
git checkout [nombre/sha1]: Nos permite mover entre ramas y entre commits, no vamos a borrar nada. Acá es donde podemos movernos en el tiempo.
git checkout -b [nombre_rama]: Nos permite crear una nueva rama sin necesidad de usar branch
```

#### Merge

git merge [rama]: Nos permite mezclar los cambios realizados en dicha rama con la rama en la que estamos.

fast-forward: los mezcla automáticamente
recursive/auto-merging: ambas ramas salieron al mismo tiempo y hay algo nuevo en la rama que la otra no recuerda, por eso hace la mezcla recursiva.
manual merge: nos va a tocar decirle a git específicamente los cambios que queremos mezclar


#### Rebase 
git rebase: hace prácticamente lo mismo que merge, cambiamos la historia de nuestro proyecto sin crear bifurcaciones del proyecto. Es mejor usar merge
Usar solo git rebase de manera local.
```
git rebase -i: de manera interactiva, nos abrira el editor que tengamos definido en la configuración de git.
```

#### Stash
Git stash: es otro de los limbos, como el staging area. Para agregar los cambios estos deben estar en el staging area.
```
git stash: salva el working directory a 
git stash list: nos muestra la lista de stash que tengamos.
git stash drop stash@{numero}: nos permite borrar un stash.
git stash apply: aplicamos el último cambio
```

#### Cherrypick 👏
```
git cherry-pick [SHA1] nos permite cambiar un commit a otra rama para salvarnos la vida.
```

### Github

Es un repositorio externo, que aloja nuestro código (y el de otros) en algún servidor de los tantos que tiene esta empresa a lo largo del mundo, entre las ventajas que nos ofrece esta plataforma es la de compartir con otros nuestro código, con otros fomentado el trabajo colaborativo, entre los desarrolladores, al mismo tiempo que el repo mantiene su integridad, y nos da funciones extra de almacenamiento, ya que si nuestra computadora se estropea, yo podria siempre recurrir a github para descargarme una copia del mismo, hay que resaltar también que github posee funcionalidades de una red social.

En git puedes hacer ```fork``` el cual hace una copia del proyecto en nuestro perfil/repositorios para poder hacerle lo que queramos sin afectar el proyecto original.

```
git clone [https/ssh]: siempre es recomendable en lo posible, usar ssh(git@github.com…) en vez de usar https ya que la primera es mucho más segura.
```

#### SSH keys 

ssh-keygen -t rsa -b 4096 -C "email@email.com". (Nos mantiene seguro dentro de github, creando llaves ssh)

#### ¿Por que cuando genero la llave ssh me pide un passphrase? 
Es la contraseña de la cuenta en github o ¿para que es?
Es una contraseña para acceder a esa llave desde tu propia compu, si le das enter - enter queda sin esa contraseña.
Es una medida se seguridad extra, en caso de que la coloques, necesitaras ingresar la contraseña cada vez que necesites usar la llave. Si haces deploy a un servidor con GIT es mejor que coloques la contraseña y bien segura.

```pbcopy < ~/.ssh/id_rsa.pub``` (Sirve para copiar esta lleva y pegarlo en un lugar dentro de github). En Windows es: cat ~/.ssh/id_rsa.pub
Este comando no funciona en Windows porque, en tu consola, pbcopy es una herramienta de copiado que depende de una herramienta llamada pb, disponible solo para entornos que funcionen con el sistema operativo de las MAC, la opción para pegar es pbpaste

Algo más fácil y rápido para usuarios Windows:
En Windows, al instalar GIT, te descarga GIT GUI.
Entonces abres GIT GUI, en el menú HELP, seleccionas la opción show KEYS y allí ves la KEY PUBLICA de GIT en tu pc si no la puedes generar con el boton GENERATE KEY.
La copias y la compartes en GITHUB y eso es todo.

Ya tenemos hecha nuestra comunicacion con github
#### Git remote
Agrega direcciones de repositorios externos a nuestro repositorio local.
```git remote add [origin] [SSH/HTTPS] Conecta un repositorio con nuestro equipo local.
git remote -v Lista las conexiones existentes.
git remote remove [origin] Elimina una conexión con algún repositorio.
```

#### Traer cambios desde repositorios externos

Hay dos formas de traer tus cambios de github a tu repo local:

### ```git fetch```
Descarga los cambios a una rama generalmente llamada ```origin/master```, seguido de esto tienes que fusionar esa rama 
### ```git fetch origin master```
 ```origin remoto | master ``` rama del remoto
 ahora tienes una rama llamada ```origin/master```
 que pueedes ver con ```git branch -a```
 ```git merge origin/master```
 si obtienes un error usar la siguiente linea
 ```git merge origin/master --allow-unrelated-histories```

### ```git pull``` 
Es ejecutar los 2 pasos anteriore ```fetch``` y ```merge``` en uno solo 
```git pull origin master```

### ```git push```
Asi subimos nuestros cambios a github:

```git push origin master```

Tambien podemos enviar los tags:

```git push origin master --tags```

Podemos enviar otras ramas:

```git push origin [otra_rama]```
