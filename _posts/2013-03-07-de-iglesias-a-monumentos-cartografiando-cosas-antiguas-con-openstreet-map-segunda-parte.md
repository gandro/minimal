---
layout: post
title: "De iglesias a  monumentos. \"Cartografiando las cosas antiguas\" 2 parte"
description: null
modified: {}
category: articles
tags: 
  - openstreetmap
  - cartografía histórica
  - osm
  - patrimonio
published: true
comments: true
---

Tras instalar  [OSMAnd en Android](https://play.google.com/store/apps/details?id=net.osmand) como navegador GPS y consultar la información histórico-patrimonial que ofrece [OpenStreetMap (OMS) para Córdoba](http://www.openstreetmap.org/?lat=37.883160000000004&lon=-4.776015&zoom=16&layers=M), me di cuenta que los datos sobre patrimonio arquitectónico en Córdoba eran muy escasos. Curiosamente, en la cartografía disponible, estaban representadas un gran número de iglesias en la zona del casco histórico (etiquetas en el modelo de datos de OMS como [amenity=place of worship](http://wiki.openstreetmap.org/wiki/Tag:amenity=place_of_worship) que además de lugares de culto, son bienes patrimoniales catalogados (BICs, Plan Especial del Casco, etc), declarados como monumentos y suficientemente conocidos.  
  
Los datos existentes sobre las iglesias están representados gráficamente como puntos o áreas. Al ser más numerosos los representados como áreas decidí empezar con ellas e ir añadiendo  la [clave OMS](http://wiki.openstreetmap.org/wiki/ES:Map_Features) correspondiente que los definiera como monumentos [historic=monument](http://wiki.openstreetma
p.org/wiki/Tag:historic=monument)
  
Los resultados, respecto a su representación, no fueron estéticamente muy satisfactorios.  No queda bien diferenciados en la renderización por defecto de OSM, así que estoy pensando en añadirlos como puntos, que sí tienen una simbología clara, o revisar otras claves como por ejemplo_ buiding=yes_.  
  
A pesar de que en el estilo "standard" de OSM no las represente,  las modificaciones si pueden ser consultadas en otros servicios/estilos basados en
OpenStreetMap como [Query-to-map](http://toolserver.org/~kolossos/qtm2/featurelist.php?key=historic&value=monument&types=areas&BBOX=-4.974,37.7773,-4.574,37.9773) o [ITO Map](http://www.itoworld.com/map/88#lat=37.88440990000009&lon=-4.7794975999999725&zoom=14).  


Resultado en ITO Map

En relación a las herramientas, para consultar y editar datos he utilizando [JOSM](http://josm.openstreetmap.de/). Aunque la interfaz es mucho más dura, JOSM se parece más las herramientas SIG con los que estoy acostumbrado a
trabajar.  Además prefiero trabajar en local  y subir los datos que hacerlo “en línea” como lo hace Potlatch. 
  
En vez de descargarme toda la información cartográfica de Córdoba, he utilizado [XAPI](http://open.mapquestapi.com/xapi/) para obtener dos ficheros XML filtrados por coordenadas (bbox=-4.88886,37.81567,-4.61421,37.93762 o lo
que es lo mismo el área del casco histórico ), claves (_amenity=place of worship_) y tipos de geometrías (_node_ y _ways_) para poder editarlos en local.  
  

(http://4.bp.blogspot.com/-ZNNAbmgnhtc/UTibkcls7GI/AAAAAAAAAfA/BXVePoTjtVo/s320/07-03-2013+14-50-40.png)

Capas XML optenidas con XAPI y cargadas en JOSM 
  
Tras una revisión de los datos, ya que no todos los lugares de culto estaban en la zona del caso o eran bienes patrimoniales, a las 24 iglesias resultantes se le añadió la clave _Historic=monument_.  Este dato está sacado de wikis varias, bibliografía, catálogos monumentales, pero principalmente de mis propios conocimiento (para algo debería servir la carrera digo yo).  
  
Después de la  verificación automática de errores, los datos actualizados fueron subidos a la base de datos de OSM, con la descripción _“[Añadiendo clave Historic a Iglesias (place_of_worship) del Casco Histórico. Áreas](http://www.openstreetmap.org/browse/changeset/15201298)”_(http://3.bp.blogspot.com/-qK2mEpWY-cc/UTicdSKC_HI/AAAAAAAAAfI/-C4xKw9CSAs/s400/historial.png)

Herramienta historial en JOSM. Se puede apreciar la actualización de la clave _historic_
  
Además de XAPI y JOSM, también he utilizado [Query-to-Map para consultas](http://toolserver.org/~kolossos/qtm2/featurelist.php?key=historic&value=*&types=points-areas&BBOX=-4.974,37.7773,-4.574,37.9773) y [OSMconverter](http://wiki.openstreetmap.org/wiki/Osmconvert#Writing_CSV_Files) para obtener listados en formato CSV tanto al inicio como al final del trabajo.  
  
  
**Primeras Conclusiones**  
  

  * La información patrimonial es muy escasa (...y por Patrimonio en Córdoba no nos podemos quejar)
  * Hay que dibujar bastante para que al menos se pueda comparar con un mapa turístico básico.
  * De las geometrías (áreas) existentes he visto bastante errores en el dibujo de la planta.
  * Hay que investigar en el tipo adecuado de representación (punto o área) pensando en la renderización básica de OSM
  * Durante la edición con JOSM, he ido encontrando herramientas interesantes como por ejemplo: revisión de histórico de objetos o información sobre los editores que han trabajado en el conjunto de datos.
  * Las herramientas del "planeta OpenStreetMap” son numerosísimas. Para una simple actualización de 24 elementos he llegado a utilizar cinco herramientas diferentes. Imagino esto se debe a que soy un _osmero_ novato,  que poco a  poco me iré dotando de mis “armas preferidas” o también, _que me guste mucho "trastear"_.
