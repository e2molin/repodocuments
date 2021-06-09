# Node JS

Javascript se crea en 1995 por **Brendan Eich** para *Netscape Navigator* como lenguaje de programación del lado del cliente. En el lado del servido siempre han dominado mlenguajes como PHP, Python o Java. Su restricción al lado cliente ha hecho que Javascript fuera considerado un lenguaje menor.

El lanzamiento de Firefox en 2002 y Safari 2003 propician la aparición de aplicaciones web con una enorme exigencia en el Javascript del navegador. En 2008 aparece Chrome con el motor V8 de Javascript desarrollado por Lars Bak que multiplicana por 20 el rendimiento del Javascript en ese navegador.

En 2009 **Ryan Dahl** sacó el motor V8 de Chrome y lo puso en el servidor, por lo que Javascript podía usarse en el backend. Esto convierte a JS en el lenguaje más usado del mundo.

Node.JS da un paso más, llevando al JS a todas partes, creando un entorno  de ejecución

* Servidor
* IoT (internet of Things)
* Cloud Computing
* Apps en tiempo real.

## 📦 Gestión de paquetes

NodeJS viene con un gestor de paquetes llamado NPM. Los paquetes que se utilizan en un proyecto se guardan en un fichero llamado **package.json**.

Se recomienda empear todo proyecto en Javascript ejecutando un

```bash
npm init -y
```

Lo que os generará un **package.json** básico que tomará el nombre del directorio de trabajo

```json
{
  "name": "nombreapp",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

Los parámetros por defecto se pueden preconfigurar para que cuando utilicemos esta opción, se rellenen correctamente.

```bash
npm config set init.author.name "Esteban E. Molin"
npm config set init.author.email "esteban.emolin@gmail.com"
npm config set init.author.url "https://www.develmap.com/cvitae/"
npm config set init.license "MIT"
npm config set init.version "0.0.1"
```

Esta información se guardará en un fichero **.npmrc** en nuestro *home*, en mi caso **C:\Users\melena** .

Dentro de este fichero además se almacenan las dependencias, los paquetes que instalamos y de los que usamos determinadas funciones. Los paquetes se instalan en un directorio llamado *node_modules*, y para instalar un paquete usamos el comando

```bash
npm install <nombre-paquete>    # Se instala dentro de la carpeta node_modules

# Se guardará como dependencia del proyecto. 
# Es el comportamiento por defecto desde NPM5, y ya no hace falta ponerlo
npm install axios --save        

npm install -g <nombre-paquete> # Se instala a nivel global en el equipo. Reservarlos para los CLI

npm install <package name>@1.2.3 # Así instalamos una versión en particular de un paquete
```

La opción *global* se utiliza  para los CLI de Vue, React o APICNIG, o para paquetes frecuentes como **nodemon**. En mi equipo los paquetes globales se instalan en la carpeta 

```bash
# Cuando se actualiza NodeJS , a veces es comveniente borrarlas a mano.
C:\Users\melena\AppData\Roaming\npm\node_modules # 📦 Paquetes globales
C:\Users\melena\AppData\Roaming\npm-cache        # Directorio de cache
```

En cualquier caso podemos obtener la ruta donde se instalan los paquetes globales así

```bash
npm config get prefix
```

Podemos también ver los paquetes globales instalados, así

```bash
npm list -g             # Muestra paquetes principales y sus dependencias
npm list -g --depth 0   # Muestra solo los paquetes principales
```
### 🔵 Otros comandos interesantes son

```bash
npm doctor                          # Comprueba que la instalación esté correcta
npm uninstall -g <nombre-paquete>   # Desinstala un paquete global
npm outdated                        # Lista módulos no actualizados
npm up <nombre-paquete>             # Actualizamos el paquete a una versión más reciente
```


Dentro de código de buenas maneras, cuando se suben los ficheros de un proyecto a GitHub, no se sube la carpeta **node_modules**. Esto nos obliga a que cuando se recupera o se clona un proyecto, se ejecute un 

```bash
npm update # Lee el package.json y se baja los paquetes especificados en las dependencias.
```

### 🔵 Dependencias del desarrollo

Existen otro tipo de dependencias que solo son necesarias cuando se desarrolla, pero no son dependencias de nuestra aplicación. Estas dependencias de desarrollo se les llama *development dependencies*. No son necesarios para que su módulo o aplicación funcionen en producción, pero pueden ser útiles al escribir el código.

```bash
npm install jasmine-node --save-dev
```

Dentro del package.json, estas dependencias tienen su lugar particular

```json
{
  // ...
  "devDependencies": {
    "jasmine-node": "^1.14.5"
  }
}
```

Los desarrolladores utilicen linters de código para asegurarse de que su código siga las prácticas recomendadas y mantener un estilo uniforme. Si bien esto es útil para el desarrollo, solo aumenta el tamaño del código que puede distribuirse y no proporciona un beneficio tangible cuando se implementa en producción.

#### 🔸 Versionamiento semántico (semver)

Como vemos lo paquetes tienen su versión 👉 a.b.c donde:

* a - *Major* (Mayor): Los cambios introducidos son grandes. El código nuevo puede hacer que nuestra App no funcione.
* b - *Minor* (Menor): Se agregan nuevas características, pero el código sigue siendo retrocompatible.
* c - *Patch* (Parches): Son conocidos también como bug fixes.

Podemos especificar que se instale una determinada versión. La versión  de eslint 6 se agrega así a nuestro proyecto.

```bash
npm i eslint@6.0.0 --save-dev
```

### 🔵 Errores

Cuando ejecutamos un comando install, en ocsaiones se producen errores. Uno de los más comunes es

> npm WARN deprecated

Son errores que avisan que una de las dependencias del paquete que instalamos está marcada como obsoleta. El desarrollador del paquete debería eliminarla y utilizar otra para el mismo fin. También nos encontramos con

> npm WARN notsup

Estos errores suelen aparecer cuando tenemos una versión de **node** o **npm** que no soporta alguna de las dependencias del paquete o simplemente estamos usando un sistema operativo donde no es necesaria. Por último destacamos los erreos de permisos.

> npm WARN checkPermissions

Error de permisos. Es bastante frecuente tener este problema y normalmente es debido a que se ha utilizado sudo para instalar paquetes con NPM, algo que nunca se debería hacer. **NUNCA** utilices **sudo** con npm (ni lo ejecutes como root). De lo contrario, es muy probable que termines teniendo estos problemas de permisos.

## ⛲️ Artículos

* Paquetes NPM interesantes [🔗 enlace](npm-packets.npm)
* Configurar un stack de desarrollo para NodeJS + ExpressJS [🔗 enlace](config-stack.npm)
* Curso de Node [🎞 video](https://www.youtube.com/watch?v=mG4U9t5nWG8&list=PLPl81lqbj-4IEnmCXEJeEXPepr8gWtsl6&index=1)
* Apuntes de node [🔗 enlace](https://apuntes.de/nodejs/#gsc.tab=0)
* https://www.digitalocean.com/community/tags/node-js?subtype=tutorial
* Faltan por revisar
  * https://www.toptal.com/javascript/a-guide-to-npm-the-node-package-manager

