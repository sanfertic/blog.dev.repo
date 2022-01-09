---
title: "Este es el segundo post"
date: 2021-10-09T01:18:05+02:00
draft: true
tags: ["Blog", "SecondPost", "Tech", "YoutubeVideo"]
categories: "Tech"
---

Instalar Hugo:
NEW:
Usar chocolatey

Ver versión hugo

OLD:
Crear las carpetas C:\Hugo  c:\Hugo\bin
Ir a https://github.com/gohugoio/hugo/releases
Descargar: https://github.com/gohugoio/hugo/releases
Extraer en: C:\Hugo\bin
Ver versión de Hugo: Hugo versión en cmd

Añadir a la variable de entorno PATH para poder ejecutar Hugo desde cualquier ubicación.
C:\ProgramData\chocolatey\lib\hugo-extended\tools
Desde el terminal crear el primer proyecto de Hugo:
hugo new site sanfertic_blog


Nos crea lo siguiente:

Archetypes: metadatos de tus datos
Content: Contenido de la web va a estar aquí
Data: puede hacer de base de datos de tu web. Siendo una web estatica puede que no se use. Si usas algún json por ejemplo puede estar aquí.
Layouts: puedes definer layout complejos para la web: header, footer, etc etc
Static: donde se van a alojar todos los elementos estáticos de la web: imagenes, ficheros css, javascript, etc
Themes: Hugo es bastante sencillo de utilizar y nos proporciona un montón de temas por defecto que nos podemos descargar desde su web e importar en nuestro proyecto.
https://themes.gohugo.io/tags/blog/
Config.toml el fichero de configuración de nuestra web.


Temas:
Cada tema de Hugo tiene su repositorio en github: https://github.com/niklasbuschmann/contrast-hugo


Theme.toml fichero de configuración del tema


Añadimos el tema al fichero de configuración:
Modificaciones en el fichero: config.toml
La url donde está el proyecto y el título.

Para comprobar que funciona lo que vamos haciendo levantamos el server de Hugo:
Hugo server

Localhost:1313

Nuevo post:
Hugo new posts/hugoBlog.md







Agregamos un submodulo desde el blog al repositorio de sanfertic.github.pages:

Generar contenido estatico:
Hugo -t nombre del tema
Hugo -t contrast-hugo
Stage, commit, push origin main

Para publicar los ficheros con draft: -D
Los ficheros en draft están preparados para publicar.

Después ir a public, add, staage, commit, push







La plantilla que se usa para generar un nuevo fichero la tenemos en la carpeta archetypes:


Cuando generamos un nuevo fichero, nos lo genera así:

Podemos crear nuevos archetypes, como posts.md y este se ejecutará siempre que creemos un fichero dentro de la carpeta posts.
Shortcodes:
Plantillas de html que podemos incluir en nuestros posts.
 shortcode-name param1 Entre { y <>}
 youtube 2xkNJL4gJ9E> ID of the youtube video


Taxonomies:
Agrupar contenido. Para ello existen tags y categories. (etiquetas y categorías.)

Añadiendo el array [taxonomies] tag = “tags” etc a config.toml el tema debería cogerlas. Pero en este caso no lo hace. Si queremos que haga una página automática con las tags que metamos, lo tenemos que revisar.
HTML Templates:
Las plantillas las tenemos en el tema: layouts:

Se pueden generar plantillas en nuestro proyecto, creando la misma estructura: layouts: _default
Hay tres tipos básicos de plantillas: list, single page y home page.
También tenemos las plantillas de secciones, con ellas podemos poner diferentes plantillas en cada una de nuestras carpetas de artículos. (En nuestro caso va a ser única, por lo menos al principio.)
Data:
Donde alojamos todos los datos: json, yml, toml. Se puede acceder a su información.
Gestión imágenes:
Nueva carpeta assets: images
