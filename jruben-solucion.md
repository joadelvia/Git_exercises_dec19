# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

> La rama será ruben-solucion (git branch ruben-solucion y git checkout ruben-solucion)

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.

`git init slideshow`

	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.

> Realizado a traves de la interfaz grafica

	c) Crea un repositorio nuevo en github llamado slideshow.

> [repositorio](http://github.com/rudahee/slideshow)

	d) Enlaza tu repositorio local con el repositorio remoto.

`git remote add origin https://github.com/rudahee/slideshow.git`

	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.

> Para ello usare varias instrucciones:

`git add .`

`git commit -m 'mi primer commit'`

`git push origin ruben-solucion`


	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
		
`mkdir ~/proyectosGit`

## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.

> realizo un par de git clone en sus correspondientes carpetas.

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
`mkdir pic`

`mv b-public-72.jpg pic`

`mv logo1.png pic`

		- Comprueba el estado del respositorio.
  
`git status`

*OUTPUT:*
~~~ 
En la rama master
Tu rama está actualizada con 'origin/master'.

Cambios no rastreados para el commit:
  (usa "git add/rm <archivo>..." para actualizar a lo que se le va a hacer commit)
  (usa "git checkout -- <archivo>..." para descartar los cambios en el directorio de trabajo)

	borrado:        b-public-72.jpg
	borrado:        logo1.png

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)

	pic/

sin cambios agregados al commit (usa "git add" y/o "git commit -a")

~~~
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js. (git mv)
> Creo la carpeta js.

`git mv *.js js`

		- Comprueba el estado del repositorio.

`git status`

*OUTPUT:*
~~~
En la rama master
Tu rama está actualizada con 'origin/master'.

Cambios a ser confirmados:
  (usa "git reset HEAD <archivo>..." para sacar del área de stage)

	renombrado:     jquery-1.9.1.js -> js/jquery-1.9.1.js
	renombrado:     jquery.cycle.all.js -> js/jquery.cycle.all.js
	renombrado:     logo_jq.js -> js/logo_jq.js
	renombrado:     logo_jq1.js -> js/logo_jq1.js

Cambios no rastreados para el commit:
  (usa "git add/rm <archivo>..." para actualizar a lo que se le va a hacer commit)
  (usa "git checkout -- <archivo>..." para descartar los cambios en el directorio de trabajo)

	borrado:        b-public-72.jpg
	borrado:        logo1.png

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)

	pic/

~~~


	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.

> La diferencia radica en como git interpreta los cambios en los ficheros. Si no usas git mv despues tendras que usar git add.

	c) Añade los cambios al área de preparación.

`git add .`

	d) Comprueba el estado del repositorio.

`git status`

*OUTPUT:*
~~~
En la rama master
Tu rama está actualizada con 'origin/master'.

Cambios a ser confirmados:
  (usa "git reset HEAD <archivo>..." para sacar del área de stage)

	renombrado:     jquery-1.9.1.js -> js/jquery-1.9.1.js
	renombrado:     jquery.cycle.all.js -> js/jquery.cycle.all.js
	renombrado:     logo_jq.js -> js/logo_jq.js
	renombrado:     logo_jq1.js -> js/logo_jq1.js
	renombrado:     b-public-72.jpg -> pic/b-public-72.jpg
	renombrado:     logo1.png -> pic/logo1.png
~~~

	e) Guarda los cambios.

`git commit -m 'ordenando los ficheros'`

	f) Comprueba el estado del repositorio.

`git status`

> me comenta que el repositorio no tiene cambios desde el ultimo comit, como es normal.

	g) Envía los cambios al repositorio remoto.

`git push origin master`

	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)

`cp logo.html logo5.html`

> Despues logo5.html lo edito con nano como corresponde.

	i) Comprueba el estado del respositorio y las diferencias en los ficheros.

`git status`

> sale el archivo editado para ser agregado.

> para ver la diferencia entre ambos ficheros estoy seguro de que deberia usar `git diff` o `git diff --cached`, pero no esta funcionando.

	j) Envia los cambios al repositorio remoto.

`git add .`

`git commit -m 'agregado logo5.html'`

`git push`

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.

`git pull`

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		- Comprueba el estado del repositorio. ¿Qué ha pasado?

> absolutamente nada, ya que al estar vacia git no la detecta.

		- Envia los cambios al repositorio remoto. ¿Cómo?

> Creo que lo mas sencillo es crear un archivo oculto para Linux y que git pueda seguir

`touch html/.oculto`

`git add .`

`git commit -m 'agregando carpeta html'`

`git push`

	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.

`git mv *.html html`

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.

`cp logo_jq2.js logo_jqq.js`

> Lo editaré con nano.

		- Comprueba el estado del respositorio e indica lo que observas.

`git status `

> Tenemos un nuevo archivo sin seguimiento.

	d) Envia los cambios al repositorio remoto.

`git add js/logo_jq2.js`

`git commit -m 'nuevo js'`

`git push`

## Ejercicio 6 - Más rutina diaria
En wc1: *no me he dado cuenta y lo he realizado con wc2*

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">

> Realizare esta tarea con Visual Studio Code para realizarla mas comodamente.
 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
 
`git add html`

`git commit -m 'separado el css y el html de logo.html'`

`git push`

 ## Ejercicio 7 - Time machine 
En 'wc2':

    a) Elimina "logo5.html", utiliza únicamente 'rm'.

`rm html/logo5.html`

		- Comprueba el estado del repositorio analizando los mensajes.

`git status`

		- Deshaz el cambio.

`git checkout html/logo5.html`

	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'

`git rm html/logo5.html`

		- Comprueba el estado del repositorio analizando los mensajes.

`git status`

> Esta vez a diferencia de la anterior, los cambios aparecen en verde. Listos para hacer un commit.

     	- Deshaz el cambio

`git reset --hard`

	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.

`git rm html/logo5.html`

`git commit -m 'eliminado logo5.html'`

`git push`
 
 
En 'wc1':

	a) Actualiza wc1.
	
`git pull`

	b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
	
> Lo realizare con Visual Studio Code.
	
	c) Envia los cambios al respositorio remoto.

`git commit -a -m 'cambios en logos.css'`
 
`git push`

 ## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.

> Lo realizare con Visual Studio Code.

 	b) Envía los cambios al repositorio remoto.
 	
`git commit -a -m 'cambios en logos.css - 2'`
 
`git push`
	 
 En 'wc2':
 
 	a) NO actualices el repositorio.
 	b) Cambia table { border-style:solid; } por table { border-style:dashed; } en logo.css.

> Visual Studio Code

 	c) Tienes que conseguir que en el respositorio remoto quede como lo acabas de modificar.
 	
> Lo mas sencillo es hacer primero un `git push` y despues empezar a trabajar desde los ultimos cambios y finalizar con un `git pull`

 Averigua quién y cuando creó el fichero 'logo.css'.
 	
`git annotate html/logo.css`
 	
## Ejercicio 9

	a) Crea wc3 en proyectosGit a partir del repositorio remoto.

`git clone https://github.com/rudahee/slideshow.git`

	b) Crea una rama llamada cambiandoEstilos.

`git branch cambiandoEstilos`

	c) Cámbiate a dicha rama.
	d) Modifica algo en logo.css.
	e) Cámbiate a la rama master.
	f) Modifica el fichero logo.html
	g) Incorpora los cambios de la rama logo.css a master.
	h) Elimina la rama cambiandoEstilos.
	
## Ejercicio 10

	a) Añade un fichero remoto que contenga la dirección del repositorio remoto que has utilizado para los ejercicios.

	
	b) Añade un fichero autoeval donde indiques como crees que has realizado estos ejercicios.
	b) Haz un pull request.