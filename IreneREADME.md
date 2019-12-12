# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
	git init slideshow
	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	c) Crea un repositorio nuevo en github llamado slideshow.
	d) Enlaza tu repositorio local con el repositorio remoto.
	git remote add origin https://github.com/iregraure/slideshow.git
	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
	git add .
	git commit -m "Ficheros extraidos"
	git push -u origin master
	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
	mkdir proyectosGit
		
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
	cd proyectosGit
	git clone https://github.com/iregraure/slideshow.git wc1
	git clone https://github.com/iregraure/slideshow.git wc2

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	cd wc1
	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
		- Comprueba el estado del respositorio.
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
		- Comprueba el estado del repositorio.
	mkdir pic
	mv slideshow_-master/*.jpg pic/
	mv slideshow_-master/*.png pic/
	git status
	git mv slideshow_-master/*.js js/
	git status
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
	Si se utiliza el comando mv git detecta que se han eliminado los ficheros y se han creado en una nueva ubicación. Si se utiliza el comando git mv git detecta que se ha cambiado el nombre de los ficheros con la nueva ruta donde se encuentran.
	c) Añade los cambios al área de preparación.
	git add .
	d) Comprueba el estado del repositorio.
	git status
	e) Guarda los cambios.
	git commit -m "Ficheros reorganizados en wc1"
	f) Comprueba el estado del repositorio.
	git status
	g) Envía los cambios al repositorio remoto.
	git push
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
	touch logo5.html
	cat slideshow_-master/logo.html >> logo5.html
	nano logo5.html
	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
	git status
	git diff
	j) Envia los cambios al repositorio remoto.
	git add logo5.html
	git commit -m "Añadido fichero logo5.html"
	git push

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
	
	cd ../wc2
	git pull
	Se actualiza el repositorio local al commit del repositorio remoto.
	Se muestra que se han movido los ficheros .js y que no han sufrido modificaciones.
	Se muestra que se ha creado el fichero logo5.html y que se han añadido 74 líneas.
	Se muestra que se han movido las imágenes.

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		- Envia los cambios al repositorio remoto. ¿Cómo?
	mkdir html
	git status --> indica que el repositorio está actualizado. Git solo registra los cambios en los ficheros, por lo que si se crea un directorio y no se añade ningún fichero lo ignora.
	Para enviar los cambios al repositorio remoto primero tenemos que crear un fichero en el directorio html
	touch html/html
	git add html/html
	git commit -m "Directorio html añadido con un fichero en blanco"
	git push
	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
	mv slideshow_-master/*.html html/
	mv *.html html/
	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		- Comprueba el estado del respositorio e indica lo que observas.
	touch js/logo_jq2.js
	cat js/logo_jq.js >> js/logo_jq2.js
	nano js/logo_jq2.js
	git status --> Al haber movido los ficheros con el comando mv, indica que se han eliminado todos los ficheros .html y se han añadido en la nueva ubicación. También indica que se ha añadido un nuevo fichero js/logo_jq2.js
	d) Envia los cambios al repositorio remoto.
	git add .
	git commit -m "Ejercicio 5 terminado"
	git push

## Ejercicio 6 - Más rutina diaria
En wc1:
	
	cd ../wc1
	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">

 	nano slideshow_-master/logo.html
	nano logo.css

	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
	git push --> Indica que no se pueden subir los cambios porque hay un conflicto.
	git pull --> Para tener el mismo árbol de directorios que en el repositorio remoto
	mv logo.css html/ --> Muevo el fichero logo.css al directorio donde debe estar. El fichero logo.html mantiene los cambios y está en el directorio html.
	git commit -m "Problema ejercicio 6 resuelto"
	git push
 
## Ejercicio 7 - Time machine 
 En 'wc2':

	cd ../wc2
	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
		 - Comprueba el estado del repositorio analizando los mensajes.
		 - Deshaz el cambio.
	rm html/logo5.html
	git status --> Indica que la rama está actualizada. Indica los comandos necesarios para añadir los cambios al repositorio y para descartar los cambios.
	git checkout html/logo5.html
 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
 		- Comprueba el estado del repositorio analizando los mensajes.
 	- Deshaz el cambio
	git rm html/logo5.html
	git status --> Indica que la rama está actualizada. Indica que se ha eliminado el fichero y el cambio se ha añadido al área de intercambio. También indica el comando a utilizar para quitar los cambios del área de intercambio.
	git reset --hard HEAD
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
	git commit -m "Fichero logo5.html eliminado"
	git pull --> Para que el repositorio local esté actualizado al último commit del repositorio remoto.
	git push

 En 'wc1':
 	a) Actualiza wc1.
	cd ../wc1
	git pull
	 b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
	nano html/logo.css

 	c) Envia los cambios al respositorio remoto.
	git commit -am "Fichero logo.css editado"
	git push
 
## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
	nano html/logo.css
 	b) Envía los cambios al repositorio remoto.
	git commit -am "Fichero logo.css editado"
	git push
 	
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
