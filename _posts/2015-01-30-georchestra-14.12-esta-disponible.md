---
layout: post
title: "geOrchestra 14.12 está disponible"
date: 2015-01-30 09:37:00
lang: es
uid: 2015-01-30
---

La PSC se complace en anunciar la inmediata disponibilidad de **geOrchestra  14,12 **,  sexto lanzamiento desde que hacemos notas de la versión.El ritmo de una versión cada 6 meses aún se mantiene gracias a la tenacidad de los desarrolladores y el apoyo continuo de las plataformas de usuarios.

Esta versión es a la vez más simple para los usuarios finales y más fácil para los administradores para integrar - el fruto de muchos informes y sugerencias que figuran en el [bugtracker](https://github.com/georchestra/georchestra/issues) (600 tickets después de octubre 2012).  
La [documentación de instalación](https://github.com/georchestra/georchestra/blob/master/README.md) completa paso a paso ahora acompañada con su pre-instalación.

<!--more-->


## Côté outils

Ahora, una ventana muestra todos los servicios predefinidos OGC: **WMS**, **WFS**, **WMTS**.

<img src="http://geobretagne.fr/pub/geOrchestra_screenshot/1-2_service_ogc_718.jpg" alt="layer finder" />

Estos servicios están configurados en archivos externos, compartida entre instancias o generados por aplicaciones de terceros. Un filtro práctico acelera la visualización de los servicios.

Una nueva opción en el menú de cada capa se muestra en todo momento los puntos de entrada de una capa para copiar/pegar en su SIG.

<img src="http://geobretagne.fr/pub/geOrchestra_screenshot/3-2_adresse_service_346.jpg" alt="layer information" />

Para el visualizador, el texto completo de conjuntos de datos de búsqueda en catálogos pueden **explotar los servivios de metadatos** para mostrar un servicio no descrito en los metadatos. Así geOrchestra aumenta la compatibilidad con los IDS de terceros.

Un mapa de contexto puede hacer referencia a un catálogo de metadatos.

<iframe width="420" height="315" src="https://www.youtube.com/embed/vX67NfFrj4o" frameborder="0" allowfullscreen></iframe>

Los **ajustes se describen mejor**: título y resumen aparecen en la capacidad de carga y el filtrado de palabras clave. Estos contextos se utilizan cada vez más para enviar paquetes entre plataformas o entre herramientas (visualizador móvil, por ejemplo).

En las características avanzadas: una geometría extraída de una primera capa puede servir como un filtro espacial sobre otro. Uno puede, por ejemplo, extraer los hogares en un área determinada [screenshot].

La **impresión es mejorada**: soporte de rotación y exportación incluyendo PNG. El diseño ha sido revisado para liberar más espacio para la hoja.

En resumen, el visualizador puede cargar addons especializados con el fin de ampliar su funcionalidad básica. Algunos ya usan "cálculo del perfil longitudinal", "generación de las cuencas hidrográficas", "anotación" ... 
Un nuevo addon activa **Google Streetview** para mostrar una vista de campo y cambiar a Street View.

<img src="http://geobretagne.fr/pub/geOrchestra_screenshot/outil_streetview.jpg" alt="" />

También hay que destacar la nueva posibilidad de **colocar el componente que genera un addon (botón, tabulaciones, campo ...) donde más te guste en la interfaz**.

Descargar, el raster ahora se extrae en su resolución nativa , siempre y cuando su hoja de metadatos mencione ese valor. Los correos electrónicos de notificación también se han mejorado.

Por último, las **traducciones españolas, francesas, alemanas**, se mantienen hasta la fecha a través de nuestras filiales internacionales :)

## Servidor de Mapas

GeoServer pasa a la versión **2.5.4** (diciembre de 2014) con la opción de geofence de apoyo.

Entre las notas de la versión acumuladas entre GeoServer 2.3.2 y 2.5.4, principalmente observamos:

 * la posibilidad de configurar el período de retención en la caché del cliente los tiles del GeoWebCache integrado (GEOS-4760)
 * una mejor referencia a capas OGC en el servicio CSW opcional (GEOS-6012)
 * mejor rendimiento en las capas vectoriales atendidas por PostGIS (GEOS-5027) 
 * se toma en cuenta los enlaces a los registros de metadatos en las capacidades de la CMA (GEOS-3387)
 * una mejor compatibilidad con el servicio WMS 1.3.0 GeoWebCache integrado (GEOS-5685)
 * y muchos más ...
Por último, la seguridad del sistema se ha fortalecido en los proxies OGC.

## Administración

La estabilidad en la contrucción se ha mejorado a través de la introducción de un [repositorio maven dedicado al proyecto](http://sdi.georchestra.org/maven/repository/), y la detección de errores javascript en la  construcción.

Además, el proyecto ahora proporciona ejemplos de configuración como para el  directorio [htdocs](https://github.com/georchestra/htdocs) y directorios de configuración mínima para [GeoServer](https://github.com/georchestra/geoserver_minimal_datadir) y [GeoNetwork](https://github.com/georchestra/geonetwork_minimal_datadir).

## Del sistema

El despliegue de una geOrchestra IDS ahora se puede hacer en 4 partes (!) :

 * para el desarrollo o para una necesidad de una sola vez para demostrar que es posible utilizar **contenedores Docker**, creados a partir de las recetas que se ofrecen en la presentación **geOrchestra/docker**(https://github.com/georchestra/docker).
 * para el despliegue rápido de todos los componentes de los IDS, incluyendo geofence, ahora es posible utilizar [ansible playbook](https://github.com/landryb/georchestra-ansible) aportado por Landry Breuil, de [CRAIG](http://craig.fr/).
 * para la implementación del middleware necesario para IDS (Apache, Tomcat, PostgreSQL, OpenLDAP), ha habido un poco más [ansible playbook](https://gitlab.geo.gob.bo/adsib/georchestra_ansible/tree/master) aportado por Daniel Quisbert de [GeoBolivia] y Juan Coronel, Daniel Jiménez de [ADSIB](http://www.adsib.gob.bo/).
 * como siempre, por la construcción de WAR del proyecto en un perfil personalizado y desplegarlos en una infraestructura dedicada, a raíz de la [documentación actualizada](https://github.com/georchestra/georchestra/blob/master/README.md). La arquitectura propuesta se basa en varias instancias tomcat por defecto y **permite la escalabilidad** del IDS.

## La comunidad

El desarrollo es todavía fuerte; [OpenHub](https://www.openhub.net/p/georchestra) reporta 1250 commits y 12 contribuyentes durante los últimos 12 meses (hacia abajo desde la caída de 2013 fue particularmente intensa).

La lista[geoerchestra-dev](https://groups.google.com/forum/#!forum/georchestra-dev) es frecuentado principalmente por hablar con alguna discusión en Inglés. No dudes en publicar en su idioma!

Una satisfacción el geOcom 2014, los participantes en la lista son más numerosos, y las preguntas más puntuales. **El GeoCOM 2015 se llevará a cabo en Alsace**, probablemente en junio. Esperamos contar con tu presencia!

## Para ir más lejos ...

Consulte las [notas de la versión](https://github.com/georchestra/georchestra/blob/master/RELEASE_NOTES.md#version-1412-stable-version) que ofrecen información detallada para la actualización.

Así mismo, recuerda visitar:

 * [integración continua](https://sdi.georchestra.org/ci/),
 * [bugtracker](https://github.com/georchestra/georchestra/issues),
 * [proyecto Kanban](https://huboard.com/georchestra/georchestra).
