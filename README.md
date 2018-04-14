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
- Crear una cuenta en **github** (https://github.com/)

# Crear directorio de trabajo

* Crear un directorio llamado ejercicio-01. (ej: D:\univalle\ejercicio-01)
* Inicializar GIT en el directorio.
  * Desde smartgit:
	* Repository > Add or Create
	* En la ventana "Add Or Create Repository", colocar la ruta del directorio creado (ej: D:\univalle\ejercicio-01)
	* En el mensaje "Should "ejercicio-01" be initialized as a new Git repository?", dar clic en el botón "Initialize".
	* Crear un archivo llamado "index.html" en el directorio creado.
	* Agregar el siguiente bloque de código:
	```
	<!DOCTYPE html>
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
		</html>
	```
	* Guardar los cambios del archivo index.html
	* Crear el directorio "maps" (Ej. C:\univalle\ejercicio01\maps)
	
	* Crear el archivo "leaf-demo.js"
	
	* Agregar el siguiente bloque de código:
	```
		// See post: http://asmaloney.com/2014/01/code/creating-an-interactive-map-with-leaflet-and-openstreetmap/

		var map = L.map( 'map', {
		  center: [20.0, 5.0],
		  minZoom: 2,
		  zoom: 2
		})

		L.tileLayer( 'http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
		  attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>',
		  subdomains: ['a', 'b', 'c']
		}).addTo( map )

		var myURL = jQuery( 'script[src$="leaf-demo.js"]' ).attr( 'src' ).replace( 'leaf-demo.js', '' )

		var myIcon = L.icon({
		  iconUrl: myURL + 'images/pin24.png',
		  iconRetinaUrl: myURL + 'images/pin48.png',
		  iconSize: [29, 24],
		  iconAnchor: [9, 21],
		  popupAnchor: [0, -14]
		})

		for ( var i=0; i < markers.length; ++i )
		{
		 L.marker( [markers[i].lat, markers[i].lng], {icon: myIcon} )
		  .bindPopup( '<a href="' + markers[i].url + '" target="_blank">' + markers[i].name + '</a>' )
		  .addTo( map );
		}
	```
	
	* Crear el archivo "markers.js"
	
	* Agregar el siguiente bloque de código:
	```
		markers = [
	   {
		 "name": "Canada",
		 "url": "https://en.wikipedia.org/wiki/Canada",
		 "lat": 56.130366,
		 "lng": -106.346771
	   },
	   {
		 "name": "Anguilla",
		 "url": "https://en.wikipedia.org/wiki/Anguilla",
		 "lat": 18.220554,
		 "lng": -63.068615
	   },
	   {
		 "name": "Barbados",
		 "url": "https://en.wikipedia.org/wiki/Barbados",
		 "lat": 13.193887,
		 "lng": -59.543198
	   },
	   {
		 "name": "United States",
		 "url": "https://en.wikipedia.org/wiki/United_States",
		 "lat": 37.090240,
		 "lng": -95.712891
	   },
	   {
		 "name": "Ireland",
		 "url": "https://en.wikipedia.org/wiki/Ireland",
		 "lat": 53.412910,
		 "lng": -8.243890
	   },
	   {
		 "name": "Scotland",
		 "url": "https://en.wikipedia.org/wiki/Scotland",
		 "lat": 56.490671,
		 "lng": -4.202646
	   },
	   {
		 "name": "England",
		 "url": "https://en.wikipedia.org/wiki/England",
		 "lat": 52.355518,
		 "lng": -1.174320
	   },
	   {
		 "name": "France",
		 "url": "https://en.wikipedia.org/wiki/France",
		 "lat": 46.227638,
		 "lng": 2.213749
	   },
	   {
		 "name": "The Netherlands",
		 "url": "https://en.wikipedia.org/wiki/The_Netherlands",
		 "lat": 52.132633,
		 "lng": 5.291266
	   },
	   {
		 "name": "Switzerland",
		 "url": "https://en.wikipedia.org/wiki/Switzerland",
		 "lat": 46.818188,
		 "lng": 8.227512
	   },
	   {
		 "name": "South Africa",
		 "url": "https://en.wikipedia.org/wiki/South_Africa",
		 "lat": -30.559482,
		 "lng": 22.937506
	   },
	   {
		 "name": "Madagascar",
		 "url": "https://en.wikipedia.org/wiki/Madagascar",
		 "lat": -18.766947,
		 "lng": 46.869107
	   },
	   {
		 "name": "Taiwan",
		 "url": "https://en.wikipedia.org/wiki/Taiwan",
		 "lat": 23.697810,
		 "lng": 120.960515
	   },
	   {
		 "name": "Japan",
		 "url": "https://en.wikipedia.org/wiki/Japan",
		 "lat": 36.204824,
		 "lng": 138.252924
	   }
	];
	```
	
	* Guardar el contenido del archivo
	
	
	* Crear el directorio "images" (Ej. C:\univalle\ejercicio01\maps\images)
	* Descargar ls siguientes imágenes y copiarlas en el directorio "images"
		* [pin24] (https://raw.githubusercontent.com/epiragauta/ejercicio01/develop/maps/images/pin24.png)
		* [pin48] (https://raw.githubusercontent.com/epiragauta/ejercicio01/develop/maps/images/pin48.png)
		
	* Abrir a smartgit
	* Seleccionar todos los archivos de la lista de archivos
	* Dar clic en el botón "Commit"
	* En la ventana, colocar un mensaje de los cambios a guardar ("Ej. Adicion de la primera versión del ejercicio)
	* Dar clic en el botón "Commit & Push".
	* Ver los cambios en el directorio del repositorio personal (https://github.com/epiragauta/ejercicio01)
	* Ejecutar el archivo index.html y abrirlo en un navegador (Google Chrome o Mozilla Firefox preferiblemente)
		
	
	
