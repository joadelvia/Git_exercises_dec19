# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.
	git init slideshow

	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	unzip slideshow_-master.zip

	c) Crea un repositorio nuevo en github llamado slideshow.
	Se crea repositorio en github

	d) Enlaza tu repositorio local con el repositorio remoto.
	git remote add slideshow https://github.com/dzr22/slideshow.git

	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.
	git add .
	git commit -m "Primer commit, se añaden los ficheros extraidos al directorio"
	git push slideshow master

	f) Crea un directorio en tu carpeta personal llamado proyectosGit.
	Se crea carpeta /home/raul/proyectosGit/
		
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
	
	git init wc1
	git clone https://github.com/dzr22/slideshow.git

	git init wc2
	git clone https://github.com/dzr22/slideshow.git

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
		mkdir pic
		mv *.jpg pic/
		mv *.png pic/
		- Comprueba el estado del respositorio.
		git status
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
		mkdir js
		git mv *.js js/
		- Comprueba el estado del repositorio.
		git status
	
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
	Al utilizar "git mv", los ficheros aparecen como renombrados y en color verde, indicando que se han movido a otro directorio. Utilizando mv nos indica que se han borrado y en color rojo.

	c) Añade los cambios al área de preparación.
	git add .

	d) Comprueba el estado del repositorio.
	git status

	e) Guarda los cambios.
	git commit -m "Se mueven las fotos y ficheros js a sus carpetas correspondientes"
	
	f) Comprueba el estado del repositorio.
	git status
	
	g) Envía los cambios al repositorio remoto.
	git push

	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
	cp logo.html logo5.html
	vim logo5.html
	git add .
	git commit -m "Se añade fichero logo5.html y se cambia la rotacion"

	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
	git status
	git show
	
	j) Envia los cambios al repositorio remoto.
	git push

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
	git pull
	Muestra los cambios realizados desde el último commit hasta ahora que subimos los cambios.
	Por ejemplo, muestra que hemos añadido el fichero logo5.html

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		mkdir html

		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		No se detecta ningún cambio (nada para hacer commit, el árbol de trabajo esta limpio)

		- Envia los cambios al repositorio remoto. ¿Cómo?
		git push
		Nos muestra un mensaje diciendo que no hay cambios (Everything up-to-date)

	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
	git mv *.html html/

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
	cp logo_jq.js logo_jq2.js
	vim logo_jq2.js	
	git add .
	git commit -m "Se añade fichero logo_jq2.js"

		- Comprueba el estado del respositorio e indica lo que observas.
		git status
		Muestra que se han movido los ficheros html a su carpeta correspondiente, y también que se ha añadido el fichero logo_jq2.js

	d) Envia los cambios al repositorio remoto.
	git push

## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">
	
	cp logo.html logo.css
	se edita logo.css según las indicaciones
 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
	git add .
	git commit -m "se crea logo.css desde logo.html"
	git pull
	Al hacer git pull muestra una ventana comentando que es necesario realizar merge, ya que hay commits diferentes entre el repositorio local y remoto. Guardamos los cambios, se realiza merge automáticamente y después muestra el resultado de git pull.
 
## Ejercicio 7 - Time machine 
 En 'wc2':

	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
	rm logo5.html
		 - Comprueba el estado del repositorio analizando los mensajes.
		git status
		muestra que los cambios no están rastreados todavía. a falta de confirmar o descartar.

		 - Deshaz el cambio.
		git checkout -- logo5.html

 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
	git rm logo5.html
 		- Comprueba el estado del repositorio analizando los mensajes.
		git rm logo5.html
		muestra que los cambios ya están en el area de intercambio.
 	- Deshaz el cambio
	git reset
	git checkout -- logo5.html
	
 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
	git rm logo5.html
	git commit -m "Se borra logo5.html"
	git push
 
 En 'wc1':
 	a) Actualiza wc1.
	git pull
	Al realizar git pull, se realiza merge desde la ventana del editor de texto, sincronizando los cambios.

	b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
	vim logo.css
	git add .
	git commit -m "Se edita logo.css"

 	c) Envia los cambios al respositorio remoto.
	git push
 
## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
	vim logo.css
	git add .
	git commit -m "Se edita logo.css, añadiendo dotted"

 	b) Envía los cambios al repositorio remoto.
	git push

 En 'wc2':
 
 	a) NO actualices el repositorio.
 	b) Cambia table { border-style:solid; } por table { border-style:dashed; } en logo.css.
	vim logo.css
	git add .
	git commit -m "Se edita logo.css, añadiendo dashed"	
	
 	c) Tienes que conseguir que en el respositorio remoto quede como lo acabas de modificar.
	git pull
	vim logo.css
	git add .
	git commit -m "Se corrigen los conflictos del fichero logo.css"
	git push

 Averigua quién y cuando creó el fichero 'logo.css'.
 	git annotate logo.css
 	
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
