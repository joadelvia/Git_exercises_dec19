# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
		Creamos el repositorio en local:
			git init slideshow
	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
			extraemos los ficheros manualmente.
	c) Crea un repositorio nuevo en github llamado slideshow.
			creamos el repositorio dentro de github.
	d) Enlaza tu repositorio local con el repositorio remoto.
			git remote add origin https://github.com/davidcebrian/Slideshow.git

	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
			git add .
			git commit -m "Añadido los ficheros al repositorio"
			git push --set-upstream origin master
	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
			nos posicionamos en la carpeta personal 
			git init proyectosGit
		
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
			cd proyectosGit para entrar al repositorio y desde ahi:
			git clone https://github.com/davidcebrian/Slideshow.git wc1
			git clone https://github.com/davidcebrian/Slideshow.git wc2

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
			nos situamos en el repositorio wc1
			creamos la carpeta pic con: mkdir pic
			mv slideshow_-master/b-public-72.jpg  pic/
			mv slideshow_-master/logo1.png  pic/
		- Comprueba el estado del respositorio.
			git status
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
			creamos el directorio js.
			git mv slideshow_-master/jquery-1.9.1.js js./
			git mv slideshow_-master/jquery.cycle.all.js js./
			git mv slideshow_-master/logo_jq1.js js./
			git mv slideshow_-master/logo_jq.js js./

		- Comprueba el estado del repositorio.
			git status
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
		con git mv los cambios se añaden directamente al área de preparación y pone renombrado delante,
		con mv normal despues debes añadir los cambios al área de preparación de los cambios aparecen como archivos borrados. 
	c) Añade los cambios al área de preparación.
		git add .
	d) Comprueba el estado del repositorio.
		git status 
	e) Guarda los cambios.
		git commit -m "Primera parte ejercicio 3"
	f) Comprueba el estado del repositorio.
		git status
	g) Envía los cambios al repositorio remoto.
		git push
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
		copio y archivo y lo renombro como logo5.html
	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
		git status
		git commit -m "añadido fichero logo5"
		git diff HEAD~1
	j) Envia los cambios al repositorio remoto.
		git push

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
		desde wc2 hacemos:
		git pull
		los mensajes nos van diciendo la cantidad de ficheros (object) que estamos trayendo a nuestro repositorio, y que se  
## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		mkdir html
		- Envia los cambios al repositorio remoto. ¿Cómo?
		git add . 
		git push
	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
		los muevo manualmente.
	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		- Comprueba el estado del respositorio e indica lo que observas
		Hay un archivo que ha cambiado y no está en el área de seguimiento.
	d) Envia los cambios al repositorio remoto.
		git add .
		git commit -m "añadido logo_jq2"
		git push
## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">
		primero hacemos un git pull
		luego copiamos ls etiquetas style y las copiamos al fichero mencionado.
 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
		git add .
		git commit -m "logo.css"
		git push
 
 ## Ejercicio 7 - Time machine 
 En 'wc2':
		primero hacemos git pull
	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
			rm html/logo5.html
		 - Comprueba el estado del repositorio analizando los mensajes.
			nos dice que el archivo logo5 en el directorio html esta borrado.
		 - Deshaz el cambio.
			git checkout html/logo5.html

 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
 		- Comprueba el estado del repositorio analizando los mensajes.
		El cambio está dentro del area de preparacion
 	- Deshaz el cambio
		git reset 
		git checkout html/logo5.html
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
		git rm html/logo5.html
		git commit -m "borrado logo5"
		git push
 
 En 'wc1':
 	a) Actualiza wc1.
	git pull
	 b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
 	c) Envia los cambios al respositorio remoto.
	git add .
	git commit -m "cambiado"
	git push
 
 ## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
 	b) Envía los cambios al repositorio remoto.
 	
 En 'wc2':
 
 	a) NO actualices el repositorio.
 	b) Cambia table { border-style:solid; } por table { border-style:dashed; } en logo.css.
 	c) Tienes que conseguir que en el respositorio remoto quede como lo acabas de modificar.
 	
 Averigua quién y cuando creó el fichero 'logo.css'.
 	
 	
## Ejercicio 9

	a) Crea wc3 en proyectosGit a partir del repositorio remoto.
	b) Crea una rama llamada cambiandoEstilos.
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
