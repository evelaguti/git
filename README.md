# Glosario 

>## GIT 

Git (pronunciado "guit"2​) es un software de control de versiones diseñado por Linus Torvalds, pensando en la eficiencia y la confiabilidad del mantenimiento de versiones de aplicaciones cuando éstas tienen un gran número de archivos de código fuente. Su propósito es llevar registro de los cambios en archivos de computadora y coordinar el trabajo que varias personas realizan sobre archivos compartidos.

>### Git fue creado por Linus Torvalds.

- ```Velocidad```: Puedes trabajar fluidamente desde tu computador

- ```Diseño sencillo```: El codigo es robusto con las herramientas necesarias, como viajar en el tiempo

- ``` Fuerte apoyo en el desarrollo no lineal```: No trabaja de manera linea, la linea del tiempo tiene bifurcaciones de manera independiente al proyecto principal

- ```Completamente distribuido```: Cada quien puede tener una copia del proyecto.

- ```Capaz de manejar grandes proyectos```: Linux, Django, Laravel, etc. Usan git
Git almacena referencias a los archivos que no se han cambiado.
Cualquier trabajo es local, puedes trabajar en cualquier parte incluso sin internet.
 

>### Tipos
- ```Local```: Vive en nuestro computador. Si le ocurre una catástrofe vamos a perder nuestro trabajo, además de que Ctrl + Z tiene cierta limitación

- ```Centralizado```: Depende de un super server donde está almacenado el repositorio. Si se quema el super server vamos a llorar y perdemos nuestro trabajo.

- ```Distribuido```: Cada participante del repositorio tiene una copia local y no afecta el trabajo del resto. No perdemos nuestro trabajo si nuestro se computador se daña, simplemente pedimos una copia a cualquier servidor donde esté almacenada la copia

>### Etapas

- ```Working Directory```: Es donde trabajamos de manera local, pero para guardarlo hay que pasarlo al Staging Area
- ```Staging Area```: Es el área de preparación, se almacenan justo antes de hacer commit
- ```Local Repository```: El repositorio local donde almacenaremos los cambios del proyecto
- ```Repository```: El repositorio en el servidor donde almacenaremos los cambios del proyecto


>### Glosario Terminal

- ```cd```  Change directory
- ```mkdir```  Make directory
- ```ls```  list - en ++windows ++deben usar dir
- ```ls -a``` nos muestra los archivos o carpetas ocultas en la terminal
- ```clear``` también se puede usar control + L
- ```touch``` crea un archivo o modifica su fecha de modificación.
- ```rm``` remove -rf(para borrar carpetas)
- 
- ```Nunca usar rm -rf / o se despiden de su pc 😞```

### VIM
- ```i``` = para poder editar
- ```:wq``` = para guardar y salir
- ```:q!``` = para salir sin guardar

### Comandos Git
- ```git init``` : Crea un repositorio de manera local y lo hará en la carpeta donde estamos posicionados o se le puede pasar [nombre_de_la_carpeta] y creará la carpeta con ese nombre.
- ```git status```: Muestra el estado del repositorio local.
- ```git add [archivo]```: Agrega el archivo al staging area ```-A``` nos agrega todos los archivos.
- ```git rm --cached [archivo]```: Sacamos el archivo del staging area.
- ```git rm -f [archivo]```: Remueve el archivo de staging y tambien del working directory.
- ```git add -n [archivo]```: No agrega el archivo a staging area sólo muestra que existe ó es ignorado.
- ```git commit -m "mensaje"```: Envía los archivos que se encuentran en 'Staging Area' a 'Local Repository' Es bueno ser descriptivos con el mensaje para saber lo que se hizo en ese commit y para informar al resto de personas.
- ```git commit -–amend```: concatena nuevos cambios con cambios previos.
- ```git tag```: Nos permite agregar etiquetas a nuestros cambios.
- ```-a``` para la anotación
- ```-m``` para el mensaje
- ```-l``` nos muestra la lista de etiquetas
- ```-f``` para renombrar
- ```-d``` para borrar
- ```git log```: Muestra la historia de todos los commits que hemos realizados.

#### Superlog
```
git config --global alias.superlog "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```

>#### Untracked files
 Son archivos que están en nuestro Working Directory, lo que aparezca en rojo es lo que se ha modificado y hay que pasarlo al Staging.
>#### Tipos de tag
 - #### tag ligera
```
git tag 1.0 "SHA" 
git tag 1.0 02512454212dfd2s...
```
- #### tag anotada
```
git tag -a 1.0 -m 'version estable' 0251245421...
git tag -a "version" -m "mensaje" "SHA"
```

>#### Opciones
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

>#### Nota
Si no se coloca el sha al final del mensaje, el tag se colocorá al ultimo commit

>#### Diff 
```
git diff [SHA1 o tag] // Nos muestra las cambios de ese commit.
``
- Rojo: fueron cambios que se quitaron
- Verde: se agregaron cosas
```

>#### Reset
```
git reset --soft sha // elimina commits hasta exclusivo el commit indicado, dejando los archivos en el staging area.
git reset --mixed sha // elimina commits hasta excluvivo el commit indicado dejando los archivos en el working directory
git reset --hard sha // elimina commits hasta excluvivo el commit indicado borrando tambien los archivos del working directory

```
>#### Ramas

Las ramas son muy importantes si quieres trabajar con un equipo y no quieres tocar la rama master para no crear conflictos,
```
git branch [nombre] se crea una nueva rama
git branch -l: listamos las ramas
git branch -d/-D [nombre]: borramos rama
git branch -m [nombre] [nombre_nuevo]: para renombrar ramas
```
>#### Checkout
```
git checkout [nombre/sha1]: Nos permite mover entre ramas y entre commits, no vamos a borrar nada. Acá es donde podemos movernos en el tiempo.
git checkout -b [nombre_rama]: Nos permite crear una nueva rama sin necesidad de usar branch
```

>#### Merge

```git merge [rama]```: Nos permite mezclar los cambios realizados en dicha rama con la rama en la que estamos.

```fast-forward```: los mezcla automáticamente
recursive/auto-merging: ambas ramas salieron al mismo tiempo y hay algo nuevo en la rama que la otra no recuerda, por eso hace la mezcla recursiva.
manual merge: nos va a tocar decirle a git específicamente los cambios que queremos mezclar


>#### Rebase 
```git rebase```: hace prácticamente lo mismo que merge, cambiamos la historia de nuestro proyecto sin crear bifurcaciones del proyecto. Es mejor usar merge
Usar solo git rebase de manera local.
```
git rebase -i: de manera interactiva, nos abrira el editor que tengamos definido en la configuración de git.
```

>#### Stash
```git stash```: es otro de los limbos, como el staging area. Para agregar los cambios estos deben estar en el staging area.
```
git stash: salva el working directory a 
git stash list: nos muestra la lista de stash que tengamos.
git stash drop stash@{numero}: nos permite borrar un stash.
git stash apply: aplicamos el último cambio
```

>#### Cherrypick 👏
```
git cherry-pick [SHA1] nos permite cambiar un commit a otra rama para salvarnos la vida.
```

>## Github

Es un repositorio externo, que aloja nuestro código (y el de otros) en algún servidor de los tantos que tiene esta empresa a lo largo del mundo, entre las ventajas que nos ofrece esta plataforma es la de compartir con otros nuestro código, con otros fomentado el trabajo colaborativo, entre los desarrolladores, al mismo tiempo que el repo mantiene su integridad, y nos da funciones extra de almacenamiento, ya que si nuestra computadora se estropea, yo podria siempre recurrir a github para descargarme una copia del mismo, hay que resaltar también que github posee funcionalidades de una red social.

En git puedes hacer ```fork``` el cual hace una copia del proyecto en nuestro perfil/repositorios para poder hacerle lo que queramos sin afectar el proyecto original.

```
git clone [https/ssh]: siempre es recomendable en lo posible, usar ssh(git@github.com…) en vez de usar https ya que la primera es mucho más segura.
```

#### SSH keys 

```ssh-keygen -t rsa -b 4096 -C "email@email.com".``` (Nos mantiene seguro dentro de github, creando llaves ssh)

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
>### Git remote
Agrega direcciones de repositorios externos a nuestro repositorio local.
```
git remote add [origin] [SSH/HTTPS] Conecta un repositorio con nuestro equipo local.
git remote -v Lista las conexiones existentes.
git remote remove [origin] Elimina una conexión con algún repositorio.
```

>#### Traer cambios desde repositorios externos

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

### Features de Github

```Unwatch``` Nos permite que nos lleguen notificaciones si hay cambios en el repositorio

```Not watching``` Se te notifica cuando participas o mencionas

```Ignoring``` Nunca ser notificado

```Stars⭐️``` Asi como en facebook se vive a base de likes, aqui se vive a base de estrellas, cuanto mas estrellas mas valorado es ese proyecto, y a su misma vez tiene muchos forks

```Fork``` Indica la cantidad de gente que hizo copia de su repositorio para poderles enviar cambios

 ```Insights contributors``` Nos permite ver el avance de nuestro proyecto podemos ver las estadísticas de nuestro proyecto en.

```traffic``` Nos muestra el trafico de nuestro proyecto
punch card (Muestra los dias que a estado trabajando)
network (Vemos el flujo de ramas)
members (Nos muestra la gente que le a hecho fork a nuestro repositorio)
dependents (Nos muestra si nuestro repositorio depende de otro, es decir de un super repositorio)

‘‘LeonidasEsteban’’ Para proyectos complejos se puede hacer un “dependecia” de repositorios o sub repositorios. Es como un proyecto dentro de otro pero es muy raro usarlos y de preferencia yo solo recomiendo un solo reposotorio’.

>### Settings:

```collaborators``` (Aqui se añade a mas gente para que colabore en este proyecto)

```branches``` (Podemos cambiar la rama principal, y proteger ramas)
CONSEJO: Protege siempre la rama master (Una vez protegida ningun cambio va a ir directamente a master tenemos que pasar por cierto proceso para que un codigo vaya a master) (Este proceso lo vemos dentro del curso)

```pull request``` (Es una forma de tomar una rama alterna por ejemplo la rama RD y no mezclarla directamente con master. Si no enviar una solicitud de mezcla desde la rama RD a la master, asi alguien mas puede ver esa solicitud, algun colaborador, etc…Y se haga un code review)

```Webhooks``` (Es la forma de poderle agregar git code a otros servicios para que hagan un auto deploy)

```Integrations & servicies``` (Incluir otros servicios como amazon, y que pueden hacer uso de nuestro repositorio)

```Deploy keys``` (Son las llaves publicas ssh de tu servidor para poder hacer git pull desde el servidor, y tener tu código en producción.)

```Pull requests``` (Vemos una lista de pull requests)

```Issues``` (Son la forma en que manejamos nuestros problemas, bugs en github. Por ejemplo: hay un bug, este no va a ser reportado si no que lo que vamos a hacer es crear un issue comentando donde hay un problema, se hace de esta manera, ocurre en tal sistema operativo, etc…)

```Proyects``` (Nos aparece nuestros proyectos)

Al crear un ```issue``` o un ```pull request```, github te permite incluir etiquetas en los mismos. Entre las etiquetas que nos pueden interesar a los que estamos comenzando a usar la plataforma se encuentran ```help wanted``` y ```good first issue```. Github anima a los desarrolladores a que marquen los “issue” y los ```pull request``` que son más aptos para los que inician en este mundo con estas etiquetas y adicionalmente se pide a la comunidad que den un apoyo especial para estos ```issue/pull request```. 
#### ¿Quiéres comenzar a colaborar en un proyecto real en Github pero aún te sientes inseguro con tus conocimientos?
 Haz una búsqueda de estás etiquetas y encontrarás miles de oportunidades para hacer tu primer aporte.

 >### Proyects 
 Github tiene un módulo para trabajar con ```scrum```, (una tabla de tareas a realizar).

```TODO```: Son las cosas por hacer.

```WIP: Work in Progress```. En que estamos trabajando.

```Bugs```: Cosas que hay que arreglar de manera prioritaria.

```Waiting for review```: nos sirve para cuando trabajamos con los pulls requests, ya que se espera que alguien revise nustro codigo.

```Done```: Cuando la tarea ha finalizado.

>### Templates para Issues

En GitHub puedes crear un template para los issues, basta con crear un archivo llamado issue_template.md y definir los lineamientos para reportar un issue, ahora al generar un nuevo issue se mostrará el nuevo template.
<!-- pagebreak -->

Recuerda que los archivos .md por dentro contienen sintaxis markdown para dar estilos a tu texto, puedes usar esta [guia](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)

>### Templates para Pull Requests

GitHub permite usar templates a la hora de generar ```pull```

Crear archivo llamado ```pull_request_template.md```
Definir los lineamientos usando sintaxis markdown

<!--pagebreak-->
Hacer commit
Ahora todo será mas ordenado cuando generen contribuciones a tu proyecto.


>### ```.gitignore```
Con el archivo ```.gitignore``` se agregan las extensiones o nombres de archivos que se deben ignorar en los commits del proyecto. 

<!--pagebreak-->
El siguiente [enlace](https://www.gitignore.io/) tiene un recurso que ayuda con éste trabajo.

>### ```Milestones```
Son tareas globales con fecha de inicio y final, los ```issues``` son tareas específicas asignadas para miembros del equipo para cumplir ese hito.

>Ejemplo:

```milestone —> remodelar casa```, Inicia en febrero y entrega en marzo.

```issues —>```

Miembro1 se encarga de pintar.
<!--pagebreak-->
Miembro2 se encarga de entregar el piso.

>### ```Github Pages```
GitHub me permite personalizar la URL de mi GitHub Pages, primero debo comprar el dominio, nosotros usamos namecheap.com.
<!--pagebreak--->
En el dashboard de namecheap vamos a manage nuestro dominio, vamos a configurar los DNS.

<!--pagebreak-->
En GitHub vamos a settings y creamos un custom URL.
Creamos en el proyecto el archivo CNAME y en el ponemos la URL del dominio que compramos.
La ip de GitHub es 192.168.252.153 - 192.168.252.154.


 
