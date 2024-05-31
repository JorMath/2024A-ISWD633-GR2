# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/1cf2d9ac-98c8-42eb-8109-217994f62e91)


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/210a3e5a-56de-480b-adc0-7456b48bc0a6)


### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/402b9927-1d88-4e0c-8ff3-bc6bc88a7d12)

![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/c1b23ca3-196f-45d0-b2e5-41d0b314207f)

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](imagenes/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/74c2fc26-67f5-4606-88b6-7c7c99372307)


**¿Qué sucede luego de la ejecución del comando?**
La terminal de comandos se queda sin poder realizar algún otro comando, es como que inicia el contenedor y se queda ahí mismo

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/f9aee198-fe37-460b-99cc-6f28c61e5130)


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/5cb0f865-7eb5-4fb4-9847-8763200f5cd0)


Verificar que el contenedor que se eliminó
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/bf1a07e9-efcb-4687-a901-04d5a7f7553b)


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/fda618fd-8f25-4c2b-84e1-07fdfca6306e)


Verificar que el contenedor que se eliminó
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/a22a5e63-d50b-4df2-89e1-940fb52cf3ea)


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
![image](https://github.com/JorMath/2024A-ISWD633-GR2/assets/94020880/b9733db0-c33e-4254-aa10-1046ac39eff9)

