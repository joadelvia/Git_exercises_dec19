# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.
crear rama: git branch solucionFranciscoPrado
cambiarse a dicha rama: git checkout solucionFranciscoPrado
## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
	cd..
	mkdir slideshow
	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	Se hace manualmente
	c) Crea un repositorio nuevo en github llamado slideshow.
	En github, repositories, new y escribes el nombre 
	d) Enlaza tu repositorio local con el repositorio remoto.
	cd slideshow
	git init
	git add .
	git commit -m "Añadidos ficheros"
	git push https://github.com/Franciscojosepi/slideshow master
	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
	mkdir proyectosGit
		
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
cd proyectosGit
mkdir wc1
cd wc1
git pull https://github.com/Franciscojosepi/slideshow master
mkdir wc2
cd wc2
git pull https://github.com/Franciscojosepi/slideshow master
## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
		Se tendra que crear la carpeta pic (mkdir pic)
		mv b-public-72.jpg pic
		mv logo1.png pic
		- Comprueba el estado del respositorio.
		git status
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
		git mv jquery.cycle.all.js js
		git mv jquery-1.9.1.js js
		git mv logo_jq.js js
		git mv logo_jq1.js js
		- Comprueba el estado del repositorio.
		git status
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
	El mv te borra los archivos y te los mete en la carpeta pic, y el git mv, aparte te los  renombra 
	c) Añade los cambios al área de preparación.
	git add .
	d) Comprueba el estado del repositorio.
	git status
	e) Guarda los cambios.
	git commit -m "Archivos desplazados"
	f) Comprueba el estado del repositorio.
	git status
	g) Envía los cambios al repositorio remoto.
	git push https://github.com/Franciscojosepi/slideshow
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
	Creo el fichero con touch logo5.html, copio el contenido de logo.html cambiando las tres primeras palabras donde aparece right.
	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
	git status
	La diferencia entre los ficheros logo.html y logo5.html es que en el primero aparece a la derecha y en el segundo aparece a la izquierda
	j) Envia los cambios al repositorio remoto.
	git add .
	git commit -m "Fichero creado"
	git push https://github.com/Franciscojosepi/slideshow

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
git pull https://github.com/Franciscojosepi/slideshow master
Esto te copia el repositorio en tu directorio local (wc2), te comprime los archivos de tu repositorio de git, los extrae en el local, y te actualiza el repositorio.


## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		creas nueva carpeta html: mkdir html
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		git status
		- Envia los cambios al repositorio remoto. ¿Cómo?
		git add .
		git commit -m "creando direct html"
		git push https://github.com/Franciscojosepi/slideshow 
	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
	git mv logo.html html
	git mv logo1.html html
	git mv logo2.html html
	git mv logo3.html html
	git mv logo4.html html
	git mv logo5.html html
	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		touch logo_jq2.js
		Copiamos el contenido de logo_jq.js cambiando los parametros
		- Comprueba el estado del respositorio e indica lo que observas.
		git status
	d) Envia los cambios al repositorio remoto.
	git add .	
	git commit -m "Archivo js creado"
	git push https://github.com/Franciscojosepi/slideshow

## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 
	nano logo.css con el contenido de la estiqueta style de logo.html
	nano logo.html y cambiamos la etiqueta style por: <link rel="stylesheet" type="text/css" href="logo.css">

 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
	git add .
	git commit -m "Archivo css creado"
	git push https://github.com/Franciscojosepi/slideshow
 
 ## Ejercicio 7 - Time machine 
 En 'wc2':

	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
		rm logo5.html
		 - Comprueba el estado del repositorio analizando los mensajes.
		git status
		 - Deshaz el cambio.
		
 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
		git rm logo5.html
 		- Comprueba el estado del repositorio analizando los mensajes.
		git status
 	- Deshaz el cambio
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
 	
 En 'wc1':
 	a) Actualiza wc1. 
	cd wc1
	git pull https://github.com/Franciscojosepi/slideshow master
	 b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
	cd slideshow_-master
	cd html
	nano logo.css y cambiamos
 	c) Envia los cambios al respositorio remoto.
 	git add .
	git commit -m "logo.css modificado"
	git push https://github.com/Franciscojosepi/slideshow 
 ## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
	nano logo.css y cambiamos
 	b) Envía los cambios al repositorio remoto.
 	git add .
	git commit -m "logo.css modificado"
	git push https://github.com/Franciscojosepi/slideshow 
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
	https://github.com/Franciscojosepi/slideshow 
	b) Añade un fichero autoeval donde indiques como crees que has realizado estos ejercicios.
	b) Haz un pull request.
