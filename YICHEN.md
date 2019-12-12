# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.

mkdir slideshow

	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
	c) Crea un repositorio nuevo en github llamado slideshow.
	d) Enlaza tu repositorio local con el repositorio remoto.

git init
git remote add origin https://github.com/Yilool/slideshow.git

	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.

git add slideshow_-master
git commit -m "primer commit, enlace dir local con rep remoto"
git push -u origin master

	f) Crea un directorio en tu carpeta personal llamado proyectosGit.

cd ~
mkdir proyectosGit

## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.

git clone https://github.com/Yilool/slideshow
git clone https://github.com/Yilool/slideshow

## Ejercicio 3 - Daily routine
En el respositorio wc1:

cd wc1

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)
mkdir imágenes
mv /home/estudiante/proyectosGit/wc1/slideshow_-master/b-public-72.jpg /home/estudiante/proyectosGit/wc1/imágenes/
mv /home/estudiante/proyectosGit/wc1/slideshow_-master/logo1.png /home/estudiante/proyectosGit/wc1/imágenes/

		- Comprueba el estado del respositorio.
git status
		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.

find /home/estudiante/proyectosGit/wc1 -name "*.js" -exec git mv {} /home/estudiante/proyectosGit/wc1/js/ \;

		- Comprueba el estado del repositorio.

	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.
Con el mv el nombre cambia al moverse y con el git mv mantiene su nonbre.

	c) Añade los cambios al área de preparación.
git add .

	d) Comprueba el estado del repositorio.
git status

	e) Guarda los cambios.
git commit -m "guardado de cambios"
	f) Comprueba el estado del repositorio.
git status
	g) Envía los cambios al repositorio remoto.
git push
	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)
	i) Comprueba el estado del respositorio y las diferencias en los ficheros.
	j) Envia los cambios al repositorio remoto.

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.
		- Comprueba el estado del repositorio. ¿Qué ha pasado?
		- Envia los cambios al repositorio remoto. ¿Cómo?
	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.
	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.
		- Comprueba el estado del respositorio e indica lo que observas.
	d) Envia los cambios al repositorio remoto.

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
