<div align="center">

# Fuentes del Sitio Web de PyCon Colombia 2020

<a href="https://github.com/PyConColombia">
  <img width="150" src="https://pyconcolombia.github.io/website-2020/static/images/logo.svg">
</a>

[![Build Status][build-badge]][build]
[![PRs Welcome][prs-badge]][prs] 
[![GitHub issues](https://img.shields.io/github/issues/PyConColombia/website-2020.svg?style=flat-square)](https://github.com/PyConColombia/website-2020/issues)
[![Twitter Jopmi](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/pyconcolombia)

Este es el repositorio del sitio web de la PyCon Colombia 2020 servido por
Github, y
construido utilizando [lektor](https://www.getlektor.com). Diseño original por [Edwin Jerez (El Hijo)
](https://github.com/soyelhijo).
</div>

# 🔀 Flujo de trabajo

Hay 2 ramas de git, `develop` y `production`.

## ⤴️ Develop

Es la rama por defecto y se despliega a través de gh-pages con Lektor a
https://pyconcolombia.github.io/website-develop/
(en http://develop.pycon.co)

## ⤴️ Production

Después de que se han ejecutado las pruebas de calidad (QA), los cambios
realizados en la rama `develop` se unen con la rama `production` y son
desplegados a través de gh-pages con Lektor a 
https://pyconcolombia.github.io/website-2020/
(pronto en http://www.pycon.co)

# 🛠 Desarrollo local

## ✅ (Opcional) Entorno Virtual

### Instalación

* Instalar [virtualenv](https://virtualenv.pypa.io/en/stable/installation/)

* ⚠️️ Requiere previa instalación de Python ⚠️

### Crear entorno virtual

```
$ virtualenv <nombre_entorno>
```

### Activar entorno virtual

#### Windows

```
$ <nombre_entorno>\Scripts\activate
```

#### Linux

```
$ source <nombre_entorno>/bin/activate
```

## ✅ Instala Lektor

### Usando pip:
```
$ pip install -U Lektor unidecode
```

### Usando conda:

```
$ conda install lektor unidecode -c conda-forge
```

## ✅ Instala (reinstala) los `plugins` locales

```
$ lektor plugins reinstall
```

## ✅ Corre el servidor local

```
$ lektor server --no-prune
```

## ⁉️ Problemas comunes

* 🔴 Si en algun momento luego de instalar python3 y crear tu virtualenv. haces `lektor server --no-prune` y ves este error:

```
RuntimeError: Click will abort further execution because Python 3 was configured to use ASCIas encoding for the environment.  Consult http://click.pocoo.org/python3/for mitigation steps.
```
Haz esto adentro de tu virtualenv:
```
export LC_ALL=en_us.UTF-8
export LANG=en_us.UTF-8
```

# 🚀 Despliegue

Gracias a _Lektor Bot_ (Plugin de lektor conectado a Github), podemos desplegar nuestra web estática en diferentes repositorios (en la rama seleccionada en configuración - `gh-pages` en nuestro caso).

La configuración de dichos repositorios se encuentra en `pyconcolombia.lektorproject`

## Integración y despliegue continuo

Este repositorio cuenta con servicio de integración continua mediante [TravisCI](https://travis-ci.org/PyConColombia/website-2020).
Cada vez que se hace un commit a `develop` o `production` el servicio despliega la página
siguiendo la configuración ubicada en el archivo [.travis.yml](https://github.com/PyConColombia/website-2020/blob/develop/.travis.yml)

## ✔️ Desarrollo

```
$ lektor deploy
```

Se desplegará el contenido de la rama `develop` en `develop.pycon.co`

## ✔️✔️ Producción

```
$ lektor deploy production
```

Se desplegará el contenido de la rama `production` en `pycon.co`


# 🛠️ Herramientasy servicios complementarios

## Cloudfare

La página utiliza [Cloudfare](https://www.cloudflare.com/) como servicio de cache y manejo de dominios y reglas 
de direccionamiento.

## Google Analytics

Las estadísticas de visitas del sitio web utiliza [Google Analytics](https://analytics.google.com/analytics/web/).

## Google Search Console

Los servicios de búsqueda y optimización utilizan la [Google Search Console](https://search.google.com/search-console/about)

___

<div align="center">

💪 Colaboradores

|[<img src="https://avatars3.githubusercontent.com/u/3627835?s=400&v=4" width="100px;"/><br /><sub><b>Gonzalo Peña</b></sub>](https://github.com/goanpeca) | [<img src="https://avatars3.githubusercontent.com/u/14989202?s=400&v=4" width="100px;"/><br /><sub><b>Alejandro E. Rendon</b></sub>](https://github.com/aerendon)|
| :---: | :---: |

</div>

[build-badge]: https://img.shields.io/travis/PyConColombia/website-2020.svg?style=flat-square
[build]: https://travis-ci.org/PyConColombia/website-2020
[license-badge]: https://img.shields.io/npm/l/all-contributors.svg?style=flat-square
[license]: https://github.com/PyConColombia/website-2020/blob/master/LICENSE.txt
[prs-badge]: https://img.shields.io/badge/Issues-welcome-brightgreen.svg?style=flat-square
[prs]: https://github.com/PyConColombia/website-2020/issues/new
