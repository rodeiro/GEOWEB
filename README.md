# GEOWEB
Google maps + leaflet + turf




+++++++++++++++++++++++++++++++++++++++++++++ HTML ++++++++++++++++++++++++++++++++++++++++++++++++++++
Fundamentos HTML + CSS + JavaScript

+++++++++++++++++++++++++++++++++++++++++++++ Leaflet ++++++++++++++++++++++++++++++++++++++++++++++++++

1. Crear un visor de mapas en Web utilizando capas tomadas de un proveedor externo (p.ej. OSM, ESRI,
Thunderforest, etc.) y capas propias (p. ej. capas que hayas creado en los trabajos tutelados - TT03,
TT04 o TT05 - de la asignatura de primer cuatrimestre, Proyectos SIG), y añadir un selector para las
mismas.

2. Partiendo de la solución previa, crear una capa adicional (que deberá ser incluida también en el
selector) formada por un conjunto de marcadores (creados ad-hoc) para diferentes puntos de interés
(p.ej. relacionados con el ámbito del ocio, los deportes, la enseñanza, la sanidad, la cultura, el
transporte, etc.), con iconos personalizados (de creación propia), y etiquetas informativas que se
visualicen al pasar el ratón sobre cada uno ellos (propiedades icon y title, respectivamente). Asimismo,
cada marcador tendrá asociado un popup, en el que se mostrará cierta información de relevancia y
una imagen, relacionados con el elemento en cuestión.
Por último, determinar el código necesario para que, cada vez que el usuario pinche sobre un
punto del mapa, se abra un popup indicando la latitud y longitud de dicho punto.
Sugerencias: usar el mismo icono para los marcadores que compartan una misma temática. En
IconFinder (https://www.iconfinder.com/), ofrece la posibilidad de elegir entre un gran número de
imágenes.

3. Modificar la solución alcanzada en la Tarea 2, teniendo en cuenta que:
    − La información asociada a los puntos de interés (i.e. coordenadas, y propiedades necesarias)
    ahora debe ser codificada en formato GeoJSON en una única variable.
    − Se deben crear diferentes capas GeoJSON de puntos de interés por ámbito (i.e. ocio, deportes,
    sanidad, etc.), las cuales serán añadidas como capas independientes al selector.
    Sugerencias: hacer uso de las opciones onEachFeature, pointToLayer, y filter, al crear las distintas
    capas GeoJSON.
Aviso: las coordenadas de un punto en formato GeoJSON siguen la convención [longitud, latitud]

4. Crear un visor de mapas en Web, a partir de información de puntos de interés en formato GeoJSON
extraída de fuentes externas, contemplando los siguientes requisitos:
    − Considerar puntos de interés para diferentes ámbitos (p. ej. tiempo libre, restauración, viajes,
    naturaleza, etc.), escogiendo al menos 4 escenarios diferentes.
    − Los puntos de interés pertenecientes a un mismo ámbito deben señalizarse con un marcador
    personalizado común. Para ello, deberá hacerse uso de alguna de las librerías de marcadores
    vistas en clase (p. ej. MakiMarkers)
    − Crear popups asociados a cada uno de los marcadores, que muestren datos de relevancia
    para el punto de interés señalado, cada vez que uno de ellos sea pulsado.
    − Integrar, en el propio visor, la funcionalidad de geoposicionamiento del usuario, señalando
    dicha posición, así como la precisión de búsqueda, y centrar la vista del mapa sobre él.
Sugerencias: para la obtención de los objetos en formato GeoJSON, se pueden utilizar distintas
alternativas:
• Hacer uso de Mapzen Metro Extracts (https://mapzen.com/metro-extracts/), y procesar con
QGIS la información extraída de una determinada zona de interés (ficheros OSM2PGSQL SHP,
OSMPGSQL GEOJSON, IMPOSM SHP, o IMPOSM GEOJSON), quedándote con aquéllos
elementos relevantes, según los escenarios temáticos que hayas decidido representar.
• Hacer uso de Mapzen Metro Extracts (ficheros PBF), o bien directamente de la Web de OSM
(https://www.openstreetmap.org/#map=5/51.500/-0.100), y cargar en una base de datos
PostGIS, los elementos de información extraídos de un área de interés. Filtrar desde PostGIS,
los elementos relevantes para tus escenarios y generar el archivo shapefile correspondiente,
que deberás convertir a GeoJSON en un paso posterior.

5. Modificar el visor de mapas en Web creado en la Tarea 4, para que se aplique la funcionalidad de
clusterización sobre sus marcadores.

6. Crear un visor de mapas en Web que muestre un mapa coroplético, incluyendo la misma funcionalidad
que la representada en el ejemplo Ejemplo-Leaflet-06.html.
Sugerencias: utilizar una capa de provincias o comunidades de España, de municipios de una
determinada comunidad, etc. y clasificar por colores en base a alguna propiedad de relevancia (p. ej.
población, número de nacimientos, edad media de sus habitantes, número de personas
desempleadas, etc.)

7. Crear un visor de mapas en Web que haga uso de algún plugin para Leaflet no visto en clase (p. ej.
map animations, minimaps, …), y explicar su funcionamiento.




+++++++++++++++++++++++++++++++++++++++++++++++ TURF ++++++++++++++++++++++++++++++++++++++++++++++

1. Completar el código proporcionado en Tarea1-P4.html, para mostrar todas aquéllas gasolineras que se
encuentran en un determinado radio de búsqueda en la ruta Barcelona-Zaragoza.

2. Haciendo uso de información (en formato GeoJSON) sobre puntos de interés en un área determinada
extraídos de fuentes externas (p.ej. farmacias, hospitales, monumentos, hoteles, iglesias,
restaurantes, paradas de metro, etc.), crear un visor de mapas en Web, capaz de encontrar aquéllos
puntos que se encuentren en un determinado radio de búsqueda respecto de un marcador que el
usuario podrá mover libremente sobre el mapa. Tener en cuenta que:
    − Se debe crear una única capa de objetos GeoJSON, pudiendo ser todos los elementos de un
    mismo ámbito o de escenarios de interés diferentes. Si se opta por la segunda opción, es
    preciso que todos los puntos posean una propiedad que permita diferenciar el ámbito de
    interés al cual pertenecen (necesario para la Tarea 3).
    − El usuario debe poder introducir el radio de búsqueda deseado a través de un campo de
    texto.
    − Se debe limpiar el resultado de la búsqueda actual en pantalla, y lanzar una nueva, cada vez
    que el usuario modifique el radio de búsqueda, o mueva el marcador de referencia sobre el
    mapa.
    − En cada búsqueda realizada, se debe informar al usuario del número total de puntos de
    interés hallados.
    − Los elementos que caigan en el radio de búsqueda deben tener un estilo diferente respecto de
    aquéllos que se encuentren fuera de la selección, para poder ser reconocidos visualmente.
    Además, asociado a cada uno de ellos se creará un popup que muestre información de
    relevancia sobre el mismo, en caso de que sea pulsado.

3. Modificar la solución alcanzada en la Tarea 2, para que la búsqueda de puntos de interés esté acotada
por un radio de búsqueda, pero también por el valor de una de sus propiedades (p.ej. gasolineras de
una determinada compañía, iglesias de un determinado siglo, etc.). Además de las características
contempladas en la Tarea 1, es importante considerar que:
    − El radio de búsqueda debe ser introducido, nuevamente, por el usuario; así como el valor de la
    propiedad que determinará los puntos de interés a seleccionar. Este último valor debe poder
    ser escogido por el usuario a través de un radiobutton, o checkbox. Tener en cuenta que si en
    la Tarea 2 se han combinado elementos de varios ámbitos, la propiedad cuyo valor podrá ser
    seleccionado entre varias opciones, debe ser aquélla que precisamente defina el ámbito de
    cada punto.
    − Se debe limpiar el resultado de la búsqueda actual en pantalla, y lanzar una nueva, cada vez
    que el usuario modifique el radio de búsqueda, la elección del valor de la propiedad de
    interés, o mueva el marcador de referencia.

4. Haciendo uso de información (en formato GeoJSON) sobre puntos de interés en un área determinada
extraídos de fuentes externas (p.ej. farmacias, hospitales, monumentos, hoteles, iglesias,
restaurantes, paradas de metro, etc.), encontrar aquél punto de interés más próximo a un marcador
que el usuario podrá mover libremente sobre el mapa. Se deben contemplar los siguientes requisitos:
    − Utilizar al menos tres conjuntos de puntos GeoJSON relacionados con diferentes ámbitos de
    interés.
    − Señalar los puntos sobre el mapa utilizando marcadores personalizados (utilizando un icono
    diferente para cada conjunto de puntos), haciendo uso de alguna librería (p. ej. MakiMarkers).
    Para cada punto, abrir un popup con información de interés cada vez que el usuario pase el
    ratón por encima de él.
    − Permitir al usuario seleccionar el conjunto/s de puntos de interés sobre los que quiere realizar
    la búsqueda, a través de una lista desplegable de valores que permita la selección múltiple,
    siendo el primer elemento de la misma la cadena vacía (i.e. indicativo de que todavía no se ha
    seleccionado ninguna opción).
    − En función de la selección realizada por el usuario, y cada vez que éste mueva el marcador de
    referencia, realizar la búsqueda del punto de interés más cercano a él de cada uno de los
    conjuntos seleccionados.
• En caso de que el usuario no haya marcado ninguna selección en la lista
desplegable, lanzar un mensaje de aviso, informando de que no se puede efectuar la
búsqueda si no se ha seleccionado antes un conjunto de búsqueda.
• Si la búsqueda tiene lugar, visualizar cada punto más cercano hallado en los
diferentes conjuntos seleccionados, utilizando el mismo icono a él asociado pero de
un tamaño mayor, y abrir automáticamente un popup con su información de
relevancia, junto con la distancia al marcador de referencia.
    − Ningún popup de los que se creen debe incluir la opción de cerrar por el usuario ('X').
    − Limpiar el resultado de la búsqueda actual en pantalla, cada vez que el usuario pulse sobre un
    punto cualquiera del mapa, o se lance una nueva búsqueda.
Sugerencias: se recomienda usar una capa diferente para cada conjunto de elementos.

5. Modificar la solución alcanzada en la Tarea 3, para que la búsqueda del elemento/s más cercanos de
los conjuntos seleccionados se realice también al pulsar sobre cualquiera de los puntos de interés que
forman dichos conjuntos.

6. Haciendo uso de información (en formato GeoJSON) sobre rutas de interés extraídas de fuentes
externas, crear un visor de mapas en Web con diferentes capas (overlays) según el tipo de ruta (p. ej.
de senderismo, de ciclismo, de carrera, de alpinismo, de cicloturismo, de kayak, en coche, a caballo, de 
alpinismo, a pie, etc.) o zona geográfica en la que se ubiquen (p. ej. en una determinada provincia, o
comunidad autónoma), incluyendo un selector para las mismas. Se debe tener en cuenta que:
    − Se deben incluir al menos 3 capas diferentes, con 4 o más rutas en cada una de ellas.
    − Si una ruta incluye puntos, estos deben visualizarse usando marcadores personalizados (p. ej.
    banderillas), y tener asociado un popup que muestre información de interés al ser pulsados.
    − Para cada ruta (i.e. feature de tipo Polyline), utilizar un estilo de visualización diferente según
    el ratón pase o no por encima de ella (de forma que sea reconocible fácilmente frente el resto
    de rutas), y mostrar un popup que indique su longitud total junto a otra información de interés
    (debiendo incluir una imagen de la ruta), cada vez que el usuario pulse sobre la misma.
    Sugerencias: puedes encontrar información de diversas rutas de interés en Wikiloc
    (http://es.wikiloc.com/wikiloc/home.do), en formato .gpx o .kml. También puedes incluir tus propias
    rutas GPS (p. ej. obtenidas a través de aplicaciones móviles de registro de datos GPS, como GPX
    Logger). En ambos casos, la transformación a formato GeoJSON se puede realizar utilizando la
    herramienta QGIS, o bien haciendo uso de páginas Web de conversión online como
    http://mapbox.github.io/togeojson/ .


7. Crear un visor de mapas en Web que haga uso de alguna de las funciones de Turf no utilizadas en
ninguna de las tareas previas, y explicar su funcionamiento.



++++++++++++++++++++++++++++++++++++++++++ GOOGLE MAPS +++++++++++++++++++++++++++++++++++++++++++++

1. Crear un visor de mapas en Web básico usando la API de Google Maps.

2. Sobre el ejemplo anterior, personalizar el estilo del mapa, definiendo una configuración de estilos para
diferentes elementos que deberá ser aplicada usando la opción styles al crear el mapa.

3. Crear un visor de mapas en Web, que incluya una instancia de la clase StyledMapType creada a partir
de la configuración de estilos definida en la tarea previa, e incorpore ésta junto a otros mapas
extraídos de fuentes externas (p. ej. OSM, Stamen, ThunderForest, ESRI, etc.) como opciones del
control de basemaps de Google Maps (además de todas o algunas de las propias capas estándar -
ROADMAP, SATELLITE, HYBRID y TERRAIN).

4. Completar la solución alcanzada en la tarea previa para incluir diferentes overlays, que se
superpondrán a la capa base que se elija en un momento dado. La visualización o no de cada uno de
los overlays deberá poder ser controlada a través de un cuadro de checkboxes que se añadirá como
control al mapa. Es importante que las opciones del checkbox aparezcan desmarcadas cada vez que se
recargue la página.
Sugerencias: puedes hacer uso de las capas usadas como overlays en la Tarea 1 de la Práctica 3, o bien
utilizar otras distintas.

5. Crear un visor de mapas en Web, con tres controles:
    − Uno que devuelva el centro del mapa a un centro de referencia (inicialmente, elegir como
    centro de referencia, aquél utilizado como centro del mapa en su creación).
    − Otro que establezca un nuevo centro de referencia.
    − Un último control que realice la geolocalización del usuario, centrando y enfocando la vista
    del mapa sobre su ubicación y añadiendo un marcador a la misma (NOTA: El marcador no
    debe ser mostrado sobre el mapa cuando se pulse cualquiera de los otros dos controles).

6. Crear un visor de mapas en Web contemplando los siguientes requisitos:
    − Cada vez que el usuario pulse sobre un punto del mapa, se debe abrir un popup con
    información posicional del mismo (i.e. latitud y longitud).

 Crear un conjunto de marcadores (ad-hoc) para distintos puntos de interés de ámbitos
diferentes (p. ej. ocio, cultura, salud, alimentación, etc.), tal que:
• Se deberá utilizar un estilo común para todos los marcadores de una misma
categoría
• Cuando el usuario pulse sobre un marcador, éste deberá comenzar a "saltar" (efecto
BOUNCE), centrando la vista del mapa sobre él y, abriendo, al mismo tiempo, un
popup con información de relevancia, que incluirá, entre otros datos, una imagen.
(NOTA: Es importante que el efecto BOUNCE se detenga cuando se pulse sobre
cualquier otro marcador o bien sobre un punto cualquiera del mapa.)
    − Sólo podrá mostrarse un popup abierto a la vez sobre el mapa.
    − Añadir un control de checkboxes al mapa que permita determinar la posibilidad de visualizar
    los marcadores en el mapa por grupos (según ámbito). Es importante que las opciones del
    checkbox aparezcan desmarcadas cada vez que se recargue la página.
    Sugerencias: puedes tomar como referencia los mismos puntos de interés creados en la Tarea 2 de la
    Práctica 3, o bien utilizar otros distintos. Para facilitar el tratamiento de los marcadores por grupos, en
    algunas acciones (p. ej. al deshabilitar el efecto BOUNCE, o visualizar los marcadores por ámbito), es
    recomendable el uso de un array para cada grupo de ellos.

7. Crear un visor de mapas en Web a partir del código proporcionado en Tarea7-P5.html, considerando
los siguientes puntos:
    − Definir un área determinada en el mapa (i.e. definir una latitud y longitud mínimas y máximas)
    − Incluir dos controles tal que según se pulse en uno u otro, se añadirá al mapa bien un
    marcador estándar, bien un marcador personalizado en una posición aleatoria dentro del área
    fijada en el paso anterior. Cada vez que se incluya un marcador éste deberá caer sobre el
    mapa (efecto DROP), tener asociada una etiqueta informativa (propiedad title), con el número
    de marcador correspondiente (i.e. si es el quinto marcador generado, su etiqueta mostrará
    "Marcador 5"), y ser añadido a un clúster.
    − La configuración del clúster (i.e. maxZoom y gridSize), podrá ser controlada dinámicamente a
    través de dos listas desplegables que serán añadidas al mapa como controles, junto a los dos
    ya existentes. Para el control de zoom del clúster se podrá escoger entre los valores 7 a 14;
    mientras que se permitirán tamaños de clúster de 40, 50, 70 y 80. Cada vez que el usuario
    escoja un valor diferente para alguno de estos controles, deberá producirse el repintado del
    clúster.
    − Como último control se añadirá otro que permita resetear el conjunto actual de marcadores
    en pantalla, que forman parte del clúster (i.e. vaciar el contenido del clúster).
    − Finalmente, cada vez que el usuario modifique el nivel de zoom del mapa se mostrará un
    popup indicando el nuevo nivel de zoom, situado en el centro del mapa.
Sugerencias: para la creación de marcadores personalizados, puedes hacer uso de los iconos ya
proporcionados con el código de referencia, o bien utilizar otros de tu gusto.

8. Partiendo del código proporcionado en Tarea8-P5.html crear un visor de mapas en Web que incluya
como basemap únicamente la capa estándar SATELLITE de Google Maps, contemplando además los
siguientes requisitos:
    − Añadir un control al mapa, en la esquina inferior izquierda, que muestre la latitud y longitud
    del punto por el que pasa el ratón al mover éste.
    − Una vez realizado el paso anterior, anotar la latitud y longitud de 5 puntos de intéres (p. ej.
    monumentos, ciudades, etc.).
    − Crear un círculo de radio acorde con las dimensiones del tipo de elementos escogidos en el
    paso previo (p. ej. si se han escogido edificios, se puede usar un radio de 200 metros; para
    ciudades, un radio de 2000 metros, etc.) y centro cualquiera (i.e. puedes ubicarlo inicialmente
    donde tú prefieras), que deberá poder ser desplazado por el usuario sobre el mapa.
    − El propósito de ese círculo será el de servir como objetivo para hacer diana en alguno de los
    puntos de interés previamente seleccionados cuando se le indique que debe proceder a la
    localización de alguno de ellos. Para ello, se añadirán dos controles al mapa:
        • Adivina: control que, al pulsarse, mostrará un mensaje de aviso indicando al usuario
        "… dónde está X", siendo X uno de los puntos de interés seleccionados, elegido al
        azar.
        • Comprueba: control que, al pulsarse, comprobará si los límites del círculo incluyen la
        localización que se le indicó al usuario que buscase. En caso de acierto, se mostrará
        un popup en la ubicación concreta informando del acierto, acompañado de una
        imagen representativa de la misma. En caso contrario, se mostrará un mensaje de
        aviso informando de la equivocación y animándole a que lo siga intentando.
NOTA: Cada vez que se proponga una nueva pregunta, se deberá cerrar el popup
que pudiese haber quedado abierto, de la búsqueda anterior.
Sugerencias: para comprobar si el círculo contiene o no al punto correspondiente a la localización a
buscar, debes averiguar la forma de obtener los límites del área abarcada por el mismo, e invocar el
método que calcula si una ubicación cae dentro de ella (consultar la API de referencia).

9. Crear un visor de mapas en Web, a partir de información de puntos de interés en formato GeoJSON
extraída de fuentes externas, contemplando los siguientes requisitos:
      − Considerar puntos de interés para diferentes ámbitos (p. ej. tiempo libre, restauración, viajes,
      naturaleza, etc.), escogiendo al menos 4 escenarios diferentes.
      − Los puntos de interés pertenecientes a un mismo ámbito deben señalizarse con un marcador
      personalizado común, utilizando imágenes diferentes como iconos.
      − Crear popups asociados a cada uno de los marcadores, que muestren datos de relevancia
      para el punto de interés señalado, cada vez que uno de ellos sea pulsado. Sólo debe
      mostrarse un único popup al mismo tiempo.
      − Añadir un control al mapa, consistente en un conjunto de checkboxes (uno por cada grupo de
      puntos de interés diferenciado), que permita mostrar u ocultar los puntos de cada ámbito
      según se marque o no la casilla correspondiente. Todas las opciones deben mostrarse
      desmarcadas al cargar la página inicialmente.
Sugerencias: puedes hacer uso de los mismos datos GeoJSON utilizados en la Tarea 4 de la Práctica 3.
Crear una capa de datos diferente por cada grupo de puntos (independientemente de que todos ellos
se extraigan de un mismo fichero o se suministren en ficheros separados).

10. Crear un visor de mapas en Web que muestre un mapa coroplético, y cumpla las siguientes
condiciones:
      − Usar una capa de objetos GeoJSON relativa a áreas (p. ej. municipios, provincias,
      comunidades, regiones, países, etc.), que puedan ser clasificables en base a alguna propiedad
      de relevancia (p. ej. población, tasa de mortalidad, renta per cápita, número de accidentes
      de tráfico, PIB, etc.) por la que se establecerá su diferenciación, de acuerdo a una escala de
      colores.
      − Modificar el estilo de cada objeto (p. ej. relleno y bordes), cada vez que se pase el ratón por
      encima de él.
      − Crear popups asociados a cada uno de los objetos, que muestren datos de interés, cada vez
      que se pulse en ellos.
Sugerencias: puedes usar los mismos datos GeoJSON empleados en la Tarea 6 de la Práctica 3.

11. Crear un visor de mapas en Web que incluya una barra de herramientas (de dibujo) para permitir la
creación ad-hoc de marcadores y figuras geométricas por el usuario. Definir estilos diferentes según el
tipo de geometría y contemplar, además, las siguientes características:
    − Tras la creación de cada dibujo, el usuario debe ser informado de la posición exacta (latitud y
    longitud) donde ha ubicado un marcador, de la longitud y área de líneas y polígonos creados,
    respectivamente; así como del centro y radio de los círculos, y límites de los rectángulos.
    − Sólo puede mostrarse un único popup abierto en el mapa, a la vez.
    − La información relativa a longitudes/áreas debe mostrarse en km/km2 .
Sugerencias: posicionar los popups, según el caso, en la localización del marcador, en el punto origen
de líneas y polígonos, en el centro de círculos y en la esquina NE de rectángulos. Delimitar la precisión
de las posiciones y medidas que se muestren por pantalla a un número determinado de decimales.

12. Crear un visor de mapas en Web que incluya la funcionalidad de búsqueda de lugares cercanos (en un
radio de 3000 metros) con respecto a un marcador que se desplazará sobre el mapa. La búsqueda se
realizará tras mover el marcador de ubicación, e incluirá un control para una de las siguientes dos
opciones (a elegir):
    − Un campo de texto (que se usará como opción query en búsquedas Text Search).
    − Una lista desplegable de tipos (que se usará como opción type en búsquedas Nearby Search).
Los resultados que se obtengan deben mostrarse con marcadores cuyo icono se tomará de la
propiedad del mismo nombre de cada resultado individual. Asociado a cada uno de ellos se creará,
además, un popup con información relevante, incluida alguna foto (en caso de existir). No podrán
mantenerse varios popup abiertos al mismo tiempo, sólo uno cada vez que un marcador de lugar sea
pulsado. Por cada nueva búsqueda que se lance, los marcadores de la búsqueda previa deberán ser
eliminados del mapa.

13. Crear un visor de mapas en Web que incluya la funcionalidad de búsqueda de lugares y
autocompletado, condicionada a uno de los 4 tipos siguientes: Todos, Establecimientos, Direcciones,
Geocoding; opciones que podrán ser escogidas en un control de tipo radiobutton. La búsqueda deberá
estar sesgada por el área de visualización actual del mapa en pantalla, y mostrar, una vez que el
usuario escoja una de las localizaciones sugeridas, un marcador en su ubicación con información de
interés, e icono correspondiente a la propiedad del mismo nombre asociada al propio resultado.
Sugerencias: incluir el campo de texto para el lugar de búsqueda como un control más del mapa, junto
con el control de tipos. Tener en cuenta, además, que escoger la opción Todos, implica no limitar la
búsqueda a ningún tipo concreto.

14. Crear un visor de mapas en web que incorpore la funcionalidad de cálculo de ruta entre dos puntos,
atendiendo a los siguientes requisitos:
    − Se crearán dos marcadores, que actuarán como origen y destino, respectivamente, y se
    podrán desplazar por el mapa. Se utilizará un icono diferente para representar cada uno de
    ellos de forma que sean fácilmente distinguibles, así como etiquetas informativas distintas y
    significativas (propiedad title).
    − Cada vez que se actualice la posición de cualquiera de los dos marcadores (i.e. al término de
    su desplazamiento), se lanzará un proceso de cálculo de las distintas rutas en coche, que
    sería posible tomar entre ambas ubicaciones.
    − Los resultados obtenidos se mostrarán usando la clase DirectionsRenderer de Google Maps, a
    través de un panel lateral anexo al mapa (NOTA: a la hora de configurar la instancia del
    objeto DirectionsRenderer, incluir la opción que deshabilita la visualización de los
    marcadores, que por defecto esta clase asocia a las posiciones de inicio y fin de la ruta; ya
    que utilizaremos los creados en el primer punto).
    − Añadir un control al mapa formado por dos cuadros de texto y un botón. Los primeros se
    utilizarán para que el usuario pueda escribir el origen y destino de la ruta, mientras que el
    botón accionará el proceso de cálculo de la misma. Es importante tener en cuenta que para
    poder proceder a ese cálculo a través de este método se debe:
        • Geocodificar los textos introducidos por el usuario como origen y destino (i.e.
        convertir la dirección / lugar a coordenadas geográficas)
        • Actualizar las posiciones de los marcadores origen y destino, a las localizaciones
        obtenidas como resultado de la geocodificación
        • Calcular la ruta, invocando la misma función utilizada al desplazar los marcadores
(NOTA: es importante invocar esta función con un timeout de diferencia respecto del
último paso anterior – por ej. setTimeout(funcion, 200))
Sugerencias: partir del código que se proporciona en Tarea14-P5.html.
