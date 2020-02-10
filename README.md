# Repodocuments

Creo un repositorio en Github llamado repodocumentos. Lo creo con un readme.md por defecto.

Carpeta de documentos en local clono el repositorio creado

```bash
git clone https://github.com/e2molin/repodocuments.git
```

Esto crea una carpeta llamada **repodocuments** que contiene el readme.md y repositorio.

Entro y modiico el README con este contenido.

Ahora puedo comprobar como está el repositorio con el comando
``` bash
#Añadir un fichero al stage
git status
```

Y en pantalla veremos

![Captura comando git status](img/cap-git-status.jpg "Captura comando git status")









## 

``` bash
#Añadir un fichero al stage
git add README.md

#Añadir todos los ficheros al stage. Hacer con cuidado para no subir cosas innecesarias. Mejor comprobar antes con un git status
git add.

#Hacer un commit al repositorio local con mensaje
git commit -m "first commit"

#Configurar el repositorio de GitHub en nuestro repositorio local (origin)
git remote add origin https://github.com/e2molin/athisto.git

#Subir nuestro repositorio local (origin) al GitHub, en este caso la rama (branch) master
git push -u origin master
```



