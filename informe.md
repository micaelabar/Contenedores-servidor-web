# Contenedores-servidor-web.
## 1. Tiempo de duración:
El tiempo de ejecución: Aproximadamente 30 minutos.
## 2. Fundamentos:
En esta práctica se trabajó con Docker y Nginx para implementar dos servidores web en contenedores separados. Docker es una herramienta de virtualización ligera que permite ejecutar aplicaciones de forma aislada dentro de contenedores, los cuales comparten el mismo núcleo del sistema operativo pero funcionan como entornos independientes. Esto hace que sean más eficientes y rápidos que las máquinas virtuales tradicionales.

Nginx es un servidor web de código abierto conocido por su alto rendimiento, su bajo consumo de recursos y su capacidad para manejar múltiples conexiones simultáneas. Es ampliamente utilizado en entornos de producción, tanto como servidor web como proxy inverso.

Durante la práctica, se crearon dos contenedores: nginx1 y nginx2, cada uno expuesto en puertos distintos (8089 y 8090). Se copió el archivo index.html desde el contenedor nginx1 al sistema anfitrión, se editó localmente para incluir información institucional, y luego se volvió a copiar al contenedor para actualizar el contenido visible desde el navegador.
## 3. Conocimientos previos.
- Iniciar Sección en Docker.
- Fundamentos de virtualización y contenedores.
- Estructura y edición de archivo HTML.
- Función u propósito de un servidor web como Nginx
## 4. Objetivos a alcanzar.
- Implementar contenedores con Nginx Utilizando Docker para levantar servidores web.
- Exponer diferentes puertos en el sistema anfitrión para acceder a cada servidor Nginx de forma independiente.
- Manipular archivos HTML dentro de los contenedores para personalizar el contenido web mostrado.
- Utilizar comandos de Docker para gestionar contenedores, incluyendo su creación, verificación y copia de archivos.
- Comprobar el funcionamiento de los servidores accediendo a los puertos correspondientes desde el navegador.
- Reforzar la comprensión del flujo de trabajo básico con Docker y la administración de servicios web en entornos aislados.
## 5. Equipo necesario:
-Computador con sistema operativo: Windows, Linux o Mac.
-Cuenta de Docker.
Conexión a Internet.
Navegador web.
## 6. Material de apoyo.
- Docker Docs https://docs.docker.com
- Linux Command Cheat Sheet https://developers.redhat.com/cheat-sheets/linux-commands-cheat-sheet​
- Guía de asignatura.
- Tutoriales en Youtube https://youtu.be/xKQM3FM-Byk
## 7. Procedimiento.
# Iniciar sesión en Google:
Primero paso se inicio la cuenta de Docker en google.
# Evidencia:
<imag!![in2 1](https://github.com/user-attachments/assets/7497fdfe-a88a-433b-86ee-fbcd9ed8f2ea)
<imag!![in2 1 1](https://github.com/user-attachments/assets/9c70aef1-ccf5-4112-a149-b6348be1e1ad)

# Crear el primer contenedor:
Segundo paso se creó un contenedor Nginx con el nombre nginx1 utilizando el siguiente comando:
```
docker run --name nginx1 -d -p 8089:80 nginx
```
# Evidencia:
<imag!![in2 2](https://github.com/user-attachments/assets/7d5e1161-02bf-4f47-88c2-4290144b53e9)

# Verificación del contenedor en ejecución:
Tercer paso para asegurarse de que el contenedor se ejecuta correctamente, se utiliza el siguiente comando:
```
docker ps
```
Tambien se abre en una nueva ventana el puerto 8089.

# Evidencia:
<imag!![inf2 3](https://github.com/user-attachments/assets/701793f2-5eb7-417a-a855-5d13148f2023)
<imag!![inf2 3 3](https://github.com/user-attachments/assets/f61e8fd6-5767-404d-89d4-7960ac6cb15a)


# Copiar archivo index.html desde el contenedor al sistema anfitrión:
Cuarto paso se copió el archivo index.html desde el contenedor nginx1 al sistema anfitrión para editarlo:
```
docker cp nginx1:/usr/share/nginx/html/index.html ./index1.html
```
# Evidencia:
<imag!
# Editar el archivo index1.html:
Quinto paso el  archivo index.html se edita para agregar información del instituto o cualquier otro contenido deseado. Para editarlo, se puede usar un editor como nano o vi:
```
nano index1.html
```
```
vi index1.html
```
# Evidencia:
<imag!
# Copiar el archivo editado nuevamente al contenedor:
Sexto paso una vez editado, se vuelve a copiar el archivo actualizado al contenedor nginx1 con el siguiente comando:
```
docker cp index1.html nginx1:/usr/share/nginx/html/index.html
```
# Evidencia:
<imag!
# Verificación de los cambios:
Séptimo paso al acceder nuevamente a http://localhost:8089 en el navegador, se debería ver la versión modificada de la página Nginx.
# Evidencia:
<imag!
