# Contenedores Servidor Web.
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
<imag!![2](https://github.com/user-attachments/assets/4b12fc0b-8655-4ef2-a074-836dacc955f9)

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

<imag!![inf2 3 2](https://github.com/user-attachments/assets/b91472f2-0152-4fee-ad81-696aecdb5b83)

# Copiar archivo index.html desde el contenedor al sistema anfitrión:
Cuarto paso se copió el archivo index.html desde el contenedor nginx1 al sistema anfitrión para editarlo:
```
docker cp nginx1:/usr/share/nginx/html/index.html ./index1.html
```
# Evidencia:
<imag!![inf2 4](https://github.com/user-attachments/assets/8f62c49d-5f1a-4c9b-a27b-c7648b504b77)

# Editar el archivo index1.html:
Quinto paso el  archivo index.html se edita para agregar información del instituto o cualquier otro contenido deseado. Para editarlo, se puede usar un editor como nano o vi:
```
nano index1.html
```
```
vi index1.html
```
# Evidencia:
<imag!![inf2 5](https://github.com/user-attachments/assets/873061a3-26b1-4cf4-9da8-4f4e2ad4b344)

# Verificación de los cambios:
Séptimo paso al acceder nuevamente a http://localhost:8089 en el navegador, se debería ver la versión modificada de la página Nginx.
# Evidencia:
<imag!![2 2 7](https://github.com/user-attachments/assets/343161c6-43e9-4c50-a326-2fbea544b95e)
## Creación del segundo contenedor Nginx:
Primer paso se repite el mismo proceso que con el primer contenedor, pero ahora para un contenedor llamado nginx2 y mapeando el puerto 8090:
```
docker run --name nginx2 -d -p 8090:80 nginx
```
# Evidencia:
<imag!![7 2](https://github.com/user-attachments/assets/e7b0bbe7-9c4a-44d0-9e32-9fb0adaf850b)

## Verificación del contenedor en ejecución:
Segundo paso se utiliza el comando docker ps nuevamente para verificar que el contenedor nginx2 se está ejecutando correctamente.
```
docker ps
```
Tambien se abre en una nueva ventana el puerto 8089.
# Evidencia:
<imag!![7 2 2](https://github.com/user-attachments/assets/71994306-8de3-4b2a-915e-addde137d205)

<imag!![7 2 3](https://github.com/user-attachments/assets/2eebec62-b4f0-4a47-ad88-02fd718a5410)

# Copiar archivo index.html desde el contenedor al sistema anfitrión:
Cuarto paso se copió el archivo index.html desde el contenedor nginx1 al sistema anfitrión para editarlo:
```
docker cp nginx2:/usr/share/nginx/html/index.html ./index.html
```
# Evidencia:
<imag!![copiar](https://github.com/user-attachments/assets/e8a39e21-93ad-459e-bb92-f5b3f7711480)

# Editar el archivo index1.html:
Quinto paso el  archivo index.html se edita para agregar información del instituto o cualquier otro contenido deseado. Para editarlo, se puede usar un editor como nano o vi:
```
nano index1.html
```
```
vi index1.html
```
# Evidencia:
<imag!![editar](https://github.com/user-attachments/assets/ee78f6ff-b52e-462d-b185-0b65f0e9db42)

## Acceso al contenedor nginx2 en el navegador:
Para verificar que el segundo contenedor está funcionando, puedes acceder a la dirección http://localhost:8090. La página predeterminada de Nginx debería aparecer.
# Evidencia:
<imag!![acceso](https://github.com/user-attachments/assets/64d2e622-a65f-40b1-98d8-5ce05e3749a3)

## 8. Resultados esperados:
Al acceder a la dirección IP proporcionada por el entorno de Play with Docker mediante los puertos 8089 y 8090, se muestra la página de bienvenida predeterminada de Nginx, lo cual indica que el servidor web Nginx fue instalado correctamente y se encuentra en funcionamiento.
# Evidencia:
<imag!![re 1](https://github.com/user-attachments/assets/c0be5187-e757-48ff-9a5f-970a3a5749d1)
<imag!![re2](https://github.com/user-attachments/assets/0e707004-2482-4f00-bdad-4b11ca3533f2)
## 9. Bibliografía:
- Docker Docs. (2025). Documentación oficial de Docker. Docker Inc.
- https://docs.docker.com
- Red Hat. (2023). Linux Commands Cheat Sheet. Red Hat Developer.
- https://developers.redhat.com/cheat-sheets/linux-commands-cheat-sheet
- PhoenixNAP. (2023). Linux Commands Cheat Sheet. PhoenixNAP Knowledge Base.
- https://phoenixnap.com/kb/linux-commands-cheat-sheet
- DevTalles. (2022). Curso Docker - Guía práctica para desarrolladores.
- https://cursos.devtalles.com/courses/docker-guia-practica
- Fazt Code. (2021). DOCKER De NOVATO a PRO! Curso completo en Español [Video]. YouTube.
- https://www.youtube.com/watch?v=CV_Uf3Dq-EU
- TechWorld with Nana. (2023). Docker Tutorial for Beginners [Full Course in 3 Hours] [Video]. YouTube.
- https://www.youtube.com/watch?v=3c-iBn73dDE




