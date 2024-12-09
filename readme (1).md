# Mateo Martinez, Pablo Ruiz de Apodaca e Ignacio Valderrama

## Descripción del Proyecto

Este proyecto crea una experiencia interactiva de realidad virtual (VR) usando A-Frame y Leaflet. Los usuarios pueden ver imágenes 360° de lugares en España y luego adivinar la ubicación de estas imágenes en un mapa interactivo. Después de hacer su selección, se les muestra la distancia entre su elección y la ubicación real de la imagen.

## Características

- **Pantalla de inicio:** Una pantalla inicial que invita a los usuarios a comenzar la experiencia.
- **Escena de A-Frame:** Muestra imágenes 360° de diferentes lugares en España.
- **Mapa interactivo:** Permite a los usuarios seleccionar en el mapa dónde creen que se tomó la imagen.
- **Pantalla de resultados:** Muestra la distancia entre la selección del usuario y la ubicación real de la imagen.

## Requisitos

- [A-Frame](https://aframe.io/releases/1.4.2/aframe.min.js): Biblioteca para crear experiencias de realidad virtual en la web.
- [Leaflet](https://unpkg.com/leaflet@1.9.4/dist/leaflet.js): Biblioteca para mapas interactivos.
- [Leaflet CSS](https://unpkg.com/leaflet@1.9.4/dist/leaflet.css): Hoja de estilos para Leaflet.

## Estructura del Código

### HTML

El archivo HTML define la estructura de la aplicación, incluyendo las diferentes pantallas y escenas. Aquí hay una breve descripción de las secciones principales:

- **Pantalla de inicio:** Un `div` con el id `startScreen` que contiene un botón para comenzar la experiencia.
- **Escena de A-Frame:** Un `a-scene` con el id `scene` que contiene un `a-sky` para mostrar las imágenes 360°.
- **Mapa interactivo:** Un `div` con el id `map` para mostrar el mapa interactivo usando Leaflet.
- **Pantalla de resultados:** Un `div` con el id `resultMap` para mostrar el mapa con la comparación de puntos.

### CSS

El CSS define estilos básicos para la aplicación, como ocultar el desbordamiento del cuerpo, estilizar los botones, y manejar la visibilidad de las diferentes pantallas.

### JavaScript

El archivo JavaScript contiene las funciones que manejan la lógica de la aplicación. Aquí están las funciones principales y su explicación:

1. **loadGalleryData()**

   - Carga los datos de la galería desde un archivo JSON y los guarda en la variable `galleryData`.

2. **getRandomImage()**

   - Selecciona una imagen aleatoria de la galería y la devuelve.

3. **startExperience()**

   - Oculta la pantalla de inicio y muestra la escena de A-Frame.
   - Carga los datos de la galería si aún no se han cargado.
   - Selecciona una imagen aleatoria y la muestra en la escena.

4. **goToMap()**

   - Oculta la escena de A-Frame y muestra el mapa interactivo.
   - Inicializa el mapa si aún no se ha hecho.

5. **goToScene()**

   - Regresa a la escena de A-Frame desde el mapa interactivo.

6. **initializeMap()**

   - Inicializa el mapa interactivo usando Leaflet.
   - Establece un evento de clic para permitir que el usuario seleccione una ubicación en el mapa.

7. **confirmClick()**
   - Verifica que el usuario haya seleccionado una ubicación en el mapa.
   - Muestra la pantalla de resultados y carga el mapa de resultados.
   - Añade marcadores para la selección del usuario y la ubicación real de la imagen.
   - Calcula y muestra la distancia entre la selección del usuario y la ubicación real.

## Estructura del Archivo JSON

El archivo `data.json` contiene información sobre las imágenes 360° y sus ubicaciones geográficas.

# Explicación de las etiquetas de `data.json`

- **id**: Un identificador único para cada imagen (por ejemplo, "Sagrada Familia").
- **src**: La ruta a la imagen 360° (por ejemplo, "Lugares/Sagrada_Familia.jpg").
- **coordinates**: Las coordenadas geográficas de la ubicación de la imagen:
  - **lat**: Latitud
  - **lng**: Longitud
