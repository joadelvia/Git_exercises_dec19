# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.

		git init slideshow

	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	c) Crea un repositorio nuevo en github llamado slideshow.
	d) Enlaza tu repositorio local con el repositorio remoto.

		cd slideshow/		
		git remote add origin https://github.com/WaterLord404/slideshow.git
		git remote -v -> vemos la union con nuestro repositorio remoto

	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.

		git add .
		git commit -m "Subiendo archivos descomprimidos"
		git push origin master

	f) Crea un directorio en tu carpeta personal llamado proyectosGit.

		cd $HOME
		mkdir proyectosGit

## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.
		
## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.

		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
		- Comprueba el estado del respositorio.
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.
		- Comprueba el estado del repositorio.

		cd /proyectosGit/wc1/slideshow_-master
		mkdir pic
		mv ./*.jpg ./pic/ && mv ./*.png ./pic/ 
		mkdir js
		mv ./*.js ./js
		git status
		
	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.

		con git mv los archivos se quedan añadidos en el staging area

	c) Añade los cambios al área de preparación.

		git add .

	d) Comprueba el estado del repositorio.

		git status

	e) Guarda los cambios.

		git commit -m "Cambios carpeta js y pic"

	f) Comprueba el estado del repositorio.

		git status

	g) Envía los cambios al repositorio remoto.

		git push origin master

	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)

		touch logo5.html

	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
		git status

	j) Envia los cambios al repositorio remoto.

		git add .
		git commit -m "cambios finales"
		git push origin master

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.
		git pull origin master

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		- Envia los cambios al repositorio remoto. ¿Cómo?

		mkdir html
		Al estar el directorio vacio git no muestra que hay cambios.		
		touch ./html/README.md
		git status -> Al crear un fichero git detecta nuestra carpeta
		git add .
		git commit -m "Carpeta html"
		git push origin master

	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.

		mv ./*.html ./html/

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		- Comprueba el estado del respositorio e indica lo que observas.

		touch logo_jq2.js
		git status
		Muestra que han desaparecido de la carpeta los archivos html (muestra que estan en el directorio html) y el nuevo fichero js

	d) Envia los cambios al repositorio remoto.

		git add .
		git commit -m "Directorio html y archivo js modificado"
		git push origin master

## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">

		touch logo.css
 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.

		git add .
		git commit -m "logo.css"
		git push origin master
 
## Ejercicio 7 - Time machine 
 En 'wc2':

	 a) Elimina "logo5.html", utiliza únicamente 'rm'.
		 - Comprueba el estado del repositorio analizando los mensajes.
		 - Deshaz el cambio.
		
		rm ./html/logo5.html
		git checkout -- logo5.html

 	b) Elimina "logo5.html" de nuevo, pero esta vez utiliza 'git rm'
 		- Comprueba el estado del repositorio analizando los mensajes.
 		- Deshaz el cambio

		git rm logo5.html
		

 	c) Por último elimina una vez más logo5.html y envía los cambios al repositorio remoto.
 
		git reset HEAD logo5.html
		git checkout -- logo5.html
 En 'wc1':
 	a) Actualiza wc1.

		cd home/proyectosGit/wc1/slideshow_-master
		git pull origin master

	b) Cambia table { border-style:none; } por table { border-style:solid; } en el fichero logo.css.
 	
	c) Envia los cambios al respositorio remoto.
	
		git add .
		git commit -m "cambio en logo.css"
		git push origin master
 
## Ejercicio 8
 
 En 'wc1':
 	
 	a) Cambia table { border-style:solid; } por table { border-style:dotted; } en logo.css.
 	b) Envía los cambios al repositorio remoto.
	
		git add .
		git commit -m "cambio en logo.css 2"
		git push origin master
 	
 En 'wc2':
 
 	a) NO actualices el repositorio.
 	b) Cambia table { border-style:solid; } por table { border-style:dashed; } en logo.css.
 	c) Tienes que conseguir que en el respositorio remoto quede como lo acabas de modificar.

		git add .
		git commit -m "cambio en logo.css 3"
		git push -f origin master
 	
 Averigua quién y cuando creó el fichero 'logo.css'.
 	
		git annotate logo.css
 	
## Ejercicio 9

	a) Crea wc3 en proyectosGit a partir del repositorio remoto.
		git init wc3
		git remote add origin https://github.com/WaterLord404/slideshow
		git pull origin master

	b) Crea una rama llamada cambiandoEstilos.

		git branch cambiandoEstilos

	c) Cámbiate a dicha rama.
	
		git checkout cambiandoEstilos

	d) Modifica algo en logo.css.

	e) Cámbiate a la rama master.

		git checkout master

	f) Modifica el fichero logo.html

	g) Incorpora los cambios de la rama logo.css a master.

		git merge cambiandoEstilos

	h) Elimina la rama cambiandoEstilos.

		git branch -d cambiandoEstilos
	
## Ejercicio 10

	a) Añade un fichero remoto que contenga la dirección del repositorio remoto que has utilizado para los ejercicios.
	b) Añade un fichero autoeval donde indiques como crees que has realizado estos ejercicios.
	b) Haz un pull request.
