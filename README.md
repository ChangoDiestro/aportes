# Uso de Git y de Github

## 1. Tu cuenta de usuario

Entra a https://github.com y crea una cuenta de usuario. Si ya tienes
una, puedes (y te recomiendo) utilizar la ya existente.

## 2. Un *fork* del repositorio principal

El repositorio principal desde el que estaremos trabajando es
https://github.com/NOMBRE/REPO; lo primero que debes hacer es
copiar el repositorio a tu espacio personal (hacer un "fork" — Una
bifurcación). Para esto, oprime el botón "Fork" en la parte superior
derecha.

## 3. *Clona* el repositorio

El siguiente paso es llevar una copia del repositorio a tu
computadora, para que puedas trabajar en él localmente. Hazlo con la
dirección que ofrece el botón verde, *clone or download*, en la parte
derecha de la pantalla.

Ojo, esto deberás hacerlo con el programa que elijas para manejar
*Git* en tu computadora. Hay muchos programas que manejan Git, y cada
uno de ustedes puede elegir el que prefiera. La
[página de descargas de Git](https://git-scm.com/downloads) ofrece
clientes para Windows, MacOS, Linux y Solaris; en Linux, te recomiendo
fuertemente utilizar el que ya viene *empaquetado* para tu
distribución.

Las instrucciones que doy en esta práctica asumen que estás usando una
interfaz Git de línea de comando; si prefieres usar una basada en
interfaz gráfica, queda para tí el convertir las instrucciones en
*ratonazos* ;-)

Si tu nombre de usuario es `fulano`, tendrás que hacer algo como:

    $ git clone https://github.com/fulano/repo.git

Eso traerá una copia del repositorio a tu computadora, desde donde
podrás trabajar.

Te recomiendo que ubiques a esta copia en un lugar donde puedas
mantenerlo a largo plazo, dado que seguiremos utilizando este
repositorio a lo largo del cursado de la materia.

Ahora, vamos a estar trabajando desde *dentro* de tu directorio
*clonado*:

    $ cd repo


## 4. Ubicación

Puedes observar que Git todavía no sabe qué hacer con el archivo que
acabas de crear:

    $ git status
	On branch master
	Your branch is up-to-date with 'origin/master'.
	Untracked files:
	  (use "git add <file>..." to include in what will be committed)

        	ejemplo.txt

    nothing added to commit but untracked files present (use "git add" to track)

## 6. Agrega tu archivo a Git y envíalo al servidor

Primero indica a Git que vas a agregar el archivo que creaste:

    $ git add fulano.txt

Y ahora crea un *commit*. Recuerda darle una descripción acorde:

    $ git commit -m 'Agrego el nombre de Fulano de Tal'

Git es un sistema *distribuido* de control de cambios. Esto significa
que tus cambios están ya registrados en la historia de Git, pero
únicamente en tu computadora. Para enviarlos a GitHub, basta con que
los *empujes* o *publiques* en el servidor:

    $ git push

## 7. Notifica de tus cambios con un *pull request*

¡Bien! Si vamos hasta aquí, lograste publicar tus cambios en
GitHub. La práctica, sin embargo, no ha sido *entregada*: Yo aún no se
nada al respecto. Si ves la página de tu repositorio en GitHub
(https://github.com/fulano/repo/ substituyendo, claro,
`fulano` por tu nombre de usuario), verás que GitHub te notifica en el
área central que estás *adelantado* al repositorio central: *This
branch is 1 commit ahead of fulano/sistop-2018-1*.

Como comentamos en clase, el uso que quiero que den a GitHub es
similar al que le darían si estuvieran corrigiendo un defecto en un
proyecto de software libre: Encontraste que el proyecto tiene un
defecto (tu práctica #1 no ha sido entregada), elaboraste la
corrección, y le envías al desarrollador del proyecto el *parche* para
que lo corrija. Esto, en el uso de GitHub, se llama un *pull request*.

En esa misma línea, del lado derecho, haz click en *Pull
request*. GitHub te mostrará un resumen de las diferencias entre mi
versión y la tuya, y si te parece correcta, te permite seleccionar el
botón verde, *Create pull request*.

Describe los cambios que hiciste, confirma tu mensaje, y GitHub te
mostrará que la solicitud ha sido creada.

¡Felicidades! Entregaste la práctica. La pelota ahora está ya en mi
cancha, me toca a mi revisar los cambios.

## 8. Configura tu copia local para seguir al repositorio raiz

A lo largo del cursado de la materia, vamos a seguir usando este
repositorio. Para poder actualizar el repositorio con las
instrucciones relevantes cuando haya nuevas prácticas, tareas o
proyectos, te recomiendo indicarle que estarás siguiendo una *rama
remota*. Pongámosle mi nombre de usuario, `fulano`:

    $ git remote add --track master fulano git://github.com/fulano/repo

Esto significa, *agrega una fuente remota en la dirección mencionada,
siguiendo la rama maestra, y dale localmente el nombre `fulano`*.

Haz la prueba: un par de días después de haber entregado esta
práctica, entra al directorio de tu repositorio e indícale:

    $ git pull fulano master

Esta instrucción significa, *trae la rama principal del repositorio
remoto `fulano`*. Cuando vuelvas a comenzar a trabajar con tu
repositorio, recuerda hacer esto para sincronizar con los últimos
cambios que yo haya enviado.
