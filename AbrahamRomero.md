# Ejercicios git 

Haz un fork del siguiente repositorio, crea una rama llamada solución  y haz una copia de este fichero en un fichero con tu nombre, a continuación  modifica el fichero creado indicando los pasos que vas realizando para resolver este ejercicio.

## Ejercicio 1 - Prepare basic git environment
Prepara el proyecto 'slideshow':

	a) Crea un repositorio nuevo llamado slideshow.

    > mkdir slideshow

	b) Extrae los ficheros que te ha proporcionado el profesor en dicho directorio.
    
    > hecho con interfaz gráfica

	c) Crea un repositorio nuevo en github llamado slideshow.

    > hecho con interfaz gŕafica

	d) Enlaza tu repositorio local con el repositorio remoto.

    > git clone https://github.com/Abrahamrc94/slideshow.git

	e) Haz lo necesario para que todos los ficheros estén disponibles en el repositorio remoto.

    > git add . 
    > git commit -m "Añadiendo ficheros"
    > git push

	f) Crea un directorio en tu carpeta personal llamado proyectosGit.

    > mkdir proyectosGit
		
## Ejercicio 2 - Create working copies
Crea dos copias del repositorio slideshow de github llamadas wc1 y wc2 dentro del directorio proyectosGit.

    > mkdir wc1
    > git clone https://github.com/Abrahamrc94/slideshow.git
    > mkdir wc2
    >  git clone https://github.com/Abrahamrc94/slideshow.git

## Ejercicio 3 - Daily routine
En el respositorio wc1:

	a) Vamos a organizar los ficheros en carpetas.
		- Mueve todas las imágenes a la carpeta pic (con el comando mv)

        > mkdir pic
        > git mv *.jpg pic
        > git mv *.png pic

		- Comprueba el estado del respositorio.

        > git status

		- Mueve todos los ficheros javascript, aquellos con extensión js, al directorio js.

        > mv *.js js

		- Comprueba el estado del repositorio.

        > git status

	b) Indica las diferencias que encuentras entre mover los ficheros de una forma o de otra.

	c) Añade los cambios al área de preparación.

    > git add .

	d) Comprueba el estado del repositorio.

    > git status

	e) Guarda los cambios.

    > git commit -m "Guardando cambios"

	f) Comprueba el estado del repositorio.

    > git status

	g) Envía los cambios al repositorio remoto.

    > git push

	h) Añade un nuevo fichero logo5.html, copia el fichero logo.html en el fichero creado y cambia el tipo de rotación de la imagen ( en la primera fila de la tabla cambia right por left, es decir cambia las tres primera palabras right por left)

    > he abierto el fichero logo.html con el editor de texto en interfaz grafica y copiado su contenido
    > nano logo5.html
    > pegamos y modificamos el fichero

	i) Comprueba el estado del respositorio y las diferencias en los ficheros.

    > git status
    > diff logo5.html logo.html

	j) Envia los cambios al repositorio remoto.

    > git add logo5.html
    > git commit -m "Añadiendo fichero logo5"
    > git push 

## Ejercicio 4 - Synchronize with others

Actualiza el respositorio wc2 y analiza los mensajes.

    > git pull

## Ejercicio 5 - Empty folder, dayli routine continued

En wc2:

	a) Crea un nuevo directorio llamado 'html'.

        > mkdir html

		- Comprueba el estado del repositorio. ¿Qué ha pasado?

        > La rama está actualizada con origin/master

		- Envia los cambios al repositorio remoto. ¿Cómo?

        > Actualmente la carpeta está vacía así que git no le hará el seguimiento 

	b) Mueve todos los ficheros html (aquellos con extensión html) al directorio html.

    > mv *.html html

	c) Crea un fichero nuevo llamado 'logo_jq2.js', copia 'logo_jqq.js' en él y cambia los parámetros (delay, speed, timeout) para la rotación del tipo 'slideY'.


    > Con interfaz grafica abrimos logo_jq.js y copiamos su contenido
    > nano logo_jq2.js
    > Pegamos y cambiamos los datos


		- Comprueba el estado del respositorio e indica lo que observas.

    >git status
    > Al mover los ficheros git detecta como que se han borrado y que la carpeta html y el archivo logo_jq2.js no tienen seguimiento 



	d) Envia los cambios al repositorio remoto.

    > git add .
    > git commit -m "Añadiendo cambios del ejercicio 5"
    > git push


## Ejercicio 6 - Más rutina diaria
En wc1:

	a) Vamos a extraer el código css del fichero logo.html a un fichero externo, para ello copia todo lo que hay entre las etiquetas **style** a un fichero llamado logo.css dentro de html y sustituye las etiquetas **style** y todo su contenido por: 

	<link rel="stylesheet" type="text/css" href="logo.css">

    > Con interfaz grafica abrimos logo_jq.js y copiamos su contenido
    > nano logo.css  y copiamos la informacion
    > nano logo.html y cambiamos la informaicón de las etiquetas style por la linea que se nos ha dado
 
	 b) Haz todo lo necesario para enviar los cambios al repositorio remoto.
 
    > git add .
    > git commit -m "Ejercicio 6"
    > git push

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

    > https://github.com/Abrahamrc94/slideshow.git

	b) Añade un fichero autoeval donde indiques como crees que has realizado estos ejercicios.
	b) Haz un pull request.