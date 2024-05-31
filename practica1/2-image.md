### Indicaciones para la práctica
El contenido solicitado entre paréntesis angulares debe ser reemplazado y los paréntesis angulares deben ser eliminados.

# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
# Una imagen es una plantilla que me ayuda a crear un contenedor con ciertos parámetros, el contenedor en sí es una instancia de esa imagen 

![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/ef1e4bd6-29ed-49e3-9bef-b3e03d6d39dc)


**¿Qué es nginx**
# nginx es un servidor web de código abierto, esto nos permite tanto visualizar como desplegar las webs en ese servidor 

Descargar la imagen  **nginx** en la versión **alpine**
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/319838cf-f0e3-42df-b011-07f0f936f9a1)


### Listar imágenes

```
docker images
```

![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/b229d87a-5df6-45ef-bbda-593b991e1260)


**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/278b46e5-a928-4a0a-a17b-1ef596319b38)


**¿Con qué algoritmo se está generando el ID de la imagen**
# Con el sha256

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/1e419532-8da0-4f09-95f5-bbf0bb93156c)


-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

