# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

fran@fran-B450M-DS3H:~/Git_exercises_dec19$ git branch solucion
fran@fran-B450M-DS3H:~/Git_exercises_dec19$ git checkout solucion
Cambiado a rama 'solucion'
fran@fran-B450M-DS3H:~/Git_exercises_dec19$ 

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
		mkdir slideshow
		cd slideshow
		git init
	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
		Listo, extraigo slideshow_master (los archivos a slideshow)
	c) Crea un repositorio nuevo en github llamado slideshow.
		Vamos a github y creamos el repositorio
	d) Enlaza tu repositorio local con el repositorio remoto.
		git remote add origin https://github.com/xXxarroyoxXx/slideshow.git
	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
		git add .
		git commit -m "Primer commit"
		git push -u origin master
	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
		cd ..
		mkdir proyectosGit

## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.

	cd proyectosGit
	git clone cd proyectosGit/
	git clone https://github.com/xXxarroyoxXx/slideshow.git wc1
	git clone https://github.com/xXxarroyoxXx/slideshow.git wc2

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
		mkdir pic
		mv b-public-72.jpg  pic
		mv logo1.png pic
		- Comprueba el estado del respositorio.
		git status (nos indica que los hemos borrado)
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
		mkdir js
		git mv *.js js
		- Comprueba el estado del repositorio.
		git status
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
		La diferencia respecto al anterior es que en el anterior , nos sale que lo hemos borrado y en este , nos lo añade directamente al stagment area.
	c) Añade los cambios al área de preparación.
		git add .
	d) Comprueba el estado del repositorio.
		git status
	e) Guarda los cambios.
		git commit -m "Ejercicio 3)e"
	f) Comprueba el estado del repositorio.
		git status
	g) Envía los cambios al repositorio remoto.
		git push origin master 
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
		nano logo5.html 

	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
		git diff HEAD~1
	j) Envia los cambios al repositorio remoto.
		git add logo5.html 
		git commit -m "Anadiendo logo5.html"
		git push origin master

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
	cd ../wc2

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		mkdir html
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
			git status
			Como git no sigue directorios vacios , el git status nos indica que no hay nada nuevo que añadir, esto tiene una solucion que la indicare en el siguiente apartado
		- Envia los cambios al repositorio remoto. ¿Cómo?
			Si queremos hacer el git push , de esa carpeta vacia , por estandar se crea un archivo llamado .keep dentro del directorio vacio y tras ello haremos el git push

			cd html 
			touch .keep
			cd ..
			git status
			git add .
			git commit -m "Subo al remoto las carpeta vacia del ejercicio 5(a"
			git push
		b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.

		mv *.html html

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		nano logo_jq2.js
		- Comprueba el estado del respositorio e indica lo que observas.
		git status 
		Nos indica que se ha creado un nuevo archivo , y que debemos añadirlo al stagment area,en caso de haber hecho el git mv *.html html, en caso de que no, todo saldra en que no le hace seguimiento
	d) Envia los cambios al repositorio remoto.
		git add .
		git commit -m "Ejercicio 5)d"
		git push

## Ejercicio 6 - Más rutina diaria
En wc1:
	cd ../wc1
	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">
	Primero nos traemos los cambios de wc2 a wc1 con 
	git pull
	(realizamos lo que nos pide, en mi caso lo hice con la interfaz grafica)

 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
 	git add .
 	git commit -m "Ejercicio 6"
 	git push
 ## Ejercicio 7 - Time machine 
 En 'wc2':
 	
 	cd ../../wc2
 	git pull

	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
	 	rm html/logo5.html
		 - Comprueba el estado del repositorio analizando los mensajes.
		 Nos indica que se ha eliminado el archivo
		 - Deshaz el cambio.
		 git restore html/logo5.html

 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
 		git rm html/logo5.html
 	- Comprueba el estado del repositorio analizando los mensajes.
 	Hemos eliminado el archivo pero estos cambios si los ha añadido a la stagment area

 	- Deshaz el cambio
 		git checkout HEAD html/logo5.html
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
 		git rm html/logo5.html
 		git commit -m "Ejercicio 7)c"
		git push 
 En 'wc1':
 	a) Actualiza wc1.
 		git pull
	 b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
	 cd ../wc1
	 nano html/logo5.html

 	c) Envia los cambios al respositorio remoto.
 	git add .
 	git commit -m "Mentira era el ejercicio 7"
 	git push
 
 ## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
 	nano html/logo.css 
 	b) Envía los cambios al repositorio remoto.
 	git commit -am "Anadimos los cambios del ejercicio 8)b1"
 	git push
 	
 En 'wc2':
 
 	a) NO actualices el repositorio.
 	Okay
 	b) Cambia table { border-style:solid; } por table { border-style:dashed; } en logo.css.
 	cd ../wc2
 	nano logo.css
 	
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