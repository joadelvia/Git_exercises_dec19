# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
		mkdir slideshow (creo el directorio slideshow)
		cd slideshow (me muevo a el)
		git init (y inicializo un nuevo repositorio vacio)
	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	c) Crea un repositorio nuevo en github llamado slideshow.
		Entro a git y creo el nuevo repositorio
		
	d) Enlaza tu repositorio local con el repositorio remoto.
		git remote add origin https://github.com/SVRoman25/slideshow.git (Enlazo el repositorio local con el remoto)
	
	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
		git add slideshow_-master/ (añado los cambios al area de preparacion)
		git commit -m "añadiendo a repositorio remoto" (hago un commit y lo añado al repositorio local )
		git push origin master (aqui lo añado al repositorio remoto)
	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
		mkdir proyectosGit
		
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
cd proyectosGit 
git clone https://github.com/SVRoman25/slideshow.git wc1
git clone https://github.com/SVRoman25/slideshow.git wc2

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
			mkdir pic (creamos la carpeta donde vamos a guardar las imagenes)
			
			mv /home/estudiante/Github/proyectosGit/wc1/slideshow_-master/*.jpg /home/estudiante/Github/proyectosGit/wc1/pic/   (movemos los archivos jpg a la carpeta pic)
			
			mv /home/estudiante/Github/proyectosGit/wc1/slideshow_-master/*.png /home/estudiante/Github/proyectosGit/wc1/pic/   (movemos los archivos png a la carpeta pic )
		
		- Comprueba el estado del respositorio.
		git status (Sale en rojo como que hemos borrado las imagenes de slideshow y que la carpeta pic es nueva no esta añadida)
		
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
		mkdir js (creamos el directorio js)
		
		git mv /home/estudiante/Github/proyectosGit/wc1/slideshow_-master/*.js /home/estudiante/Github/proyectosGit/wc1/js	(movemos los archivos a js)
		
		- Comprueba el estado del repositorio.
		git status (ahora no sale en verdad como que hemos renombrado los ficheros .js y los hemos movido a la carpeta js)
		
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
	
	La diferencia que veo es que cuando usas mv solo detecta como que los archivos han sido borrados y no se han añadido al area de preparacion mientras que con git mv los mueve al area de preparacion y sale en verde como renombrado
	
	c) Añade los cambios al área de preparación.
		git add pic 
		git add slideshow_-master
		No hace falta hacer git add a js por que al hacer git mv ya se añadio 
		
	d) Comprueba el estado del repositorio.
	git status 
	
	e) Guarda los cambios.
	git commit -m "añadiendo los cambios de wc1"
	
	f) Comprueba el estado del repositorio.
	git status (nos dice que el arbo lde trabajo esta limpio y que la rama esta adelantada por un commit)
	
	g) Envía los cambios al repositorio remoto.
	git push origin master
	
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
	touch logo5.html 
	cp logo.html logo5.html
	
	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
	git status (Nos muestra en rojo un archivo sin seguimiento que es el creado por nosotros logo5.html)
	
	j) Envia los cambios al repositorio remoto.
	git add slideshow_-master
	git commit -m "añadiendo logo5.html"
	git push origin master

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
git pull 
no sale los archivos que hemos modificado con anterioridad la cantidad total de archivos modificados y el numero de inserciones echos en un archivo 

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		mkdir html
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		git status (nos dice que la rama esta actualizada nada)
		
		- Envia los cambios al repositorio remoto. ¿Cómo?
		tendremos que introducir algo en el nuevo directorio 
	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
	mv /home/estudiante/Github/proyectosGit/wc2/slideshow_-master/*.html /home/estudiante/Github/proyectosGit/wc2/html

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		- Comprueba el estado del respositorio e indica lo que observas.
	touch logo_jq2.js
	cp logo_jq.js logo_jq2.js 
	cambiamos lo indicado en el enunciado
	git status (nos sale en rojo los cambios de la carpeta html y del logo indicando que no esta añadido al area de preparacion)
	
	d) Envia los cambios al repositorio remoto.
	git add .
	git commit -m "añadiendo cambios en wc2"
	git push origin master

## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">

 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
 
 ## Ejercicio 7 - Time machine 
 En 'wc2':

	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
		 - Comprueba el estado del repositorio analizando los mensajes.
		 - Deshaz el cambio.
 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
 		- Comprueba el estado del repositorio analizando los mensajes.
 	- Deshaz el cambio
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
 
 En 'wc1':
 	a) Actualiza wc1.
	 b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
 	c) Envia los cambios al respositorio remoto.
 
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
