Ejemplo con el API LEAFLET
--

Creación de un Mapa con [Leaflet](http://leafletjs.com) y [OpenStreetMap](https://www.openstreetmap.org).

(Las imagenes son tomadas de: [clker.com](http://www.clker.com/clipart-google-maps-pin-blue.html))

13 Abril 2018


- Requerimientos

- Alguno de los siguientes clientes (Recomiendo SmartGIT)
- GIT (Opcional) : https://git-scm.com/
- SmartGIT (Opcional) : https://www.syntevo.com/smartgit/
- Editor de Texto: Notepad++ (https://notepad-plus-plus.org/)

# Crear directorio de trabajo

* Crear un directorio llamado ejercicio-01. (ej: D:\univalle\ejercicio-01)
* Inicializar GIT en el directorio.
  * Desde smartgit:
	* Repository > Add or Create
	* En la ventana "Add Or Create Repository", colocar la ruta del directorio creado (ej: D:\univalle\ejercicio-01)
	* En el mensaje "Should "ejercicio-01" be initialized as a new Git repository?", dar clic en el botón "Initialize".
	* Crear un archivo llamado "index.html" en el directorio creado.
	* Agregar el siguiente bloque de código:
	`<!DOCTYPE html>
		<html lang="en-US" xmlns="http://www.w3.org/1999/xhtml">
		  <head profile="http://gmpg.org/xfn/11">
			<title>Mapa de Ejemplo</title>
			<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />

			<link rel="stylesheet" type="text/css" href="http://cdn.leafletjs.com/leaflet/v0.7.7/leaflet.css" />

			<script type='text/javascript' src='http://ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js'></script>
			<script type='text/javascript' src='http://cdn.leafletjs.com/leaflet/v0.7.7/leaflet.js'></script>
		  </head>

		  <body>
			<h1>Mapa (Leaflet)</h1>

			<p>Mapa interactivo con puntos sobre algunos paises

			<div id="map" style="width: 800px; height: 440px; border: 1px solid #AAA;"></div>

			
			<script type='text/javascript' src='maps/markers.json'></script>
			<script type='text/javascript' src='maps/leaf-demo.js'></script>
		  </body>
		</html>`
