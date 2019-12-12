# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
		cd Desktop 
		mkdir slideshow 
		cd slideshow
		git init
	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	c) Crea un repositorio nuevo en github llamado slideshow.
	d) Enlaza tu repositorio local con el repositorio remoto.
		git add slideshow_-master
		git commit -m "Primer commit"
		git remote add origin https://github.com/alvarodachez/slideshow.git
	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
		git push -u origin master
	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
		cd Desktop
		mkdir proyectosGit
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
	cd proyectosGit
	git clone https://github.com/alvarodachez/slideshow.git
	mv slideshow wc1
	git clone https://github.com/alvarodachez/slideshow.git
	mv slideshow wc2
## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
			mkdir pic
			mv slideshow_-master/*.png pic/
			mv slideshow_-master/*.jpg pic/
			
		- Comprueba el estado del respositorio.
			git status
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
			git mv slideshow_-master/*.js js/
		- Comprueba el estado del repositorio.
			git status
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
			Al hacer el git mv te lo añade directamente al area de preparacion, mientras cuando hemos usado el mv no se añaden al area de preparacion
	c) Añade los cambios al área de preparación.
		git add pic/
		git add slideshow/
	d) Comprueba el estado del repositorio.
		git status
	e) Guarda los cambios.
		git commit -m "organizacion carpetas"
	f) Comprueba el estado del repositorio.
		git status
	g) Envía los cambios al repositorio remoto.
		git push
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
		cp slideshow_-master/logo.html logo5.html                    	
	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
		git status
	j) Envia los cambios al repositorio remoto.
		git push

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
	cd ..
	cd wc2
	git pull
	"al hacer el git pull git se trae todos los cambios del repositorio remoto al local, te informa de los añadidos y los eliminados"
## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
			git status
			"no te muestra que se ha realizado ningun cambio porque el directorio html esta vacio"
		- Envia los cambios al repositorio remoto. ¿Cómo?
			touch html/README.md
			git push 
	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
		git mv slideshow_-master/*html html/

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		cp js/logo_jq.js logo_jq2.js
		- Comprueba el estado del respositorio e indica lo que observas.
			git status 
			"los html añadidos se encuentran en el area de preparacion, y el logo en el area de trabajo"
	d) Envia los cambios al repositorio remoto.
		git add logo_jq2.js
		git commit -m "organizados htmls y logojq2"
		git push

## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">

 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
 		git add html/
 		git commit -m "extraido css de logo"
 		git push

 ## Ejercicio 7 - Time machine 
 En 'wc2':

	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
		 - Comprueba el estado del repositorio analizando los mensajes.
		 	git rm logo5.html
		 	git status
		 	"nos dice que añadamos el rm con add para que puedan ser "commiteados" y que podemos deshacer el cambio"
		 - Deshaz el cambio.
		 	git checkout logo5.html
 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
 		git rm logo5.html

 		- Comprueba el estado del repositorio analizando los mensajes.
 		git status
 		"ha añadido el borrado al area de preparacion "	
 	- Deshaz el cambio
 		git reset logo5.html
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
 		git rm logo5.html
 		git commit -m "borrado logo5"
 		git push
 En 'wc1':
 	a) Actualiza wc1.
 		git pull
	 b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
 	c) Envia los cambios al respositorio remoto.
 		git add html/logo.css
 		git commit -m "cambiado el logo.css"
		git push
 ## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
 	b) Envía los cambios al repositorio remoto.
 		git add html/logo.css
 		git commit -m "cambiado el logo.css segunda vez"
		git push
 	
 En 'wc2':
 
 	a) NO actualices el repositorio.
 	b) Cambia table { border-style:solid; } por table { border-style:dashed; } en logo.css.
 	c) Tienes que conseguir que en el respositorio remoto quede como lo acabas de modificar.
 	
 Averigua quién y cuando creó el fichero 'logo.css'.
 	git log "lo hizo Alvaro Rueda Sanchez <ruedasanchez99@gmail.com> a las Thu Dec 12 14:09:22 2019 +0100"
 	
## Ejercicio 9

	a) Crea wc3 en proyectosGit a partir del repositorio remoto.
		cd proyectosGit
		git clone https://github.com/alvarodachez/slideshow.git
		mv slideshow wc3
	b) Crea una rama llamada cambiandoEstilos.
		git branch cambiandoEstilos
	c) Cámbiate a dicha rama.
		git checkout cambiandoEstilos
	d) Modifica algo en logo.css.
	e) Cámbiate a la rama master.
		git checkout master
	f) Modifica el fichero logo.html
	g) Incorpora los cambios de la rama cambiandoEstilos a master.
		git merge cambiandoEstilos
	h) Elimina la rama cambiandoEstilos.
		git checkout -d cambiandoEstilos
	
## Ejercicio 10

	a) Añade un fichero remoto que contenga la dirección del repositorio remoto que has utilizado para los ejercicios.
	b) Añade un fichero autoeval donde indiques como crees que has realizado estos ejercicios.
	b) Haz un pull request.