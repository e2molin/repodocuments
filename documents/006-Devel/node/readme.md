# Node JS

Javascript se crea en 1995 por **Brendan Eich** para *Netscape Navigator* como lenguaje de programación del lado del cliente. En el lado del servido siempre han dominado mlenguajes como PHP, Python o Java. Su restricción al lado cliente ha hecho que Javascript fuera considerado un lenguaje menor.

El lanzamiento de Firefox en 2002 y Safari 2003 propician la aparición de aplicaciones web con una enorme exigencia en el Javascript del navegador. En 2008 aparece Chrome con el motor V8 de Javascript desarrollado por Lars Bak que multiplicana por 20 el rendimiento del Javascript en ese navegador.

En 2009 **Ryan Dahl** sacó el motor V8 de Chrome y lo puso en el servidor,  por lo que Jaascript podía usarse en el backend. Esto convierte a JS en el lenguaje más usado del mundo.

Node.JS da un paso más, llevando al JS a todas partes

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
Dentro de este fichero además se almacenan las dependencias, los paquetes que instalamos y de los que usamos determinadas funciones. Los paquetes se instalan en un directorio llamado *node_modules*, y para instalar un paquete usamos el comando

```bash
npm install <nombre-paquete> # Se instala dentro de la carpeta node_modules
npm install -g <nombre-paquete> # Se instala a nivel global en el equipo

npm install <package name>@1.2.3 # Así instalamos una versión en particular de un paquete
```

La opción *global* se utiliza  para los CLI de Vue, React o APICNIG, o para paquetes frecuentes como **nodemon**. En mi equipo los paquetes globales se instalan en la carpeta 

```bash
# Cuando se actualiza NodeJS , a veces es comveniente borrarlas a mano.
C:\Users\melena\AppData\Roaming\npm\node_modules # 📦 Paquetes globales
C:\Users\melena\AppData\Roaming\npm-cache        # Directorio de cache
```

Dentro de código de buebas maneras, cuando se suben los ficheros de un proyecto a GitHub, no se sube la carpeta **node_modules**. Esto nos obliga a que cuando se recupera o se clona un proyecto, se ejecute un 

```bash
npm update # Lee el package.json y se baja los paquetes especificados en las dependencias.
```





## Artículos

* Paquetes NPM interesantes [🔗 enlace](npm-packets.npm)
* Configurar un stack de desarrollo para NodeJS + ExpressJS [🔗 enlace](config-stack.npm)
* Curso de Node [🎞 video](https://www.youtube.com/watch?v=mG4U9t5nWG8&list=PLPl81lqbj-4IEnmCXEJeEXPepr8gWtsl6&index=1)

https://www.toptal.com/javascript/a-guide-to-npm-the-node-package-manager
