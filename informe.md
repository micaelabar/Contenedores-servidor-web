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
# Paso 1. Iniciar sesión en Google:
Primero se inicio la cuenta de Docker en google.
# Evidencia:
<imag!![in2 1](https://github.com/user-attachments/assets/a7d03692-5f10-4ea7-a255-c0fa4ac1c128)
<imag![in2 2](https://github.com/user-attachments/assets/8b22c324-7977-48fb-802f-c3e5aaf74759)

# Paso 2: Crear el primer contenedor:
Segundo, se creó un contenedor Nginx con el nombre nginx1 utilizando el siguiente comando:
```
docker run --name nginx1 -d -p 8089:80 nginx
```
# Evidencia:
<imag![in2 3](https://github.com/user-attachments/assets/3cce2760-dd5f-43d1-aa9e-15d7d8719621)

# Paso 3: Verificación del contenedor en ejecución:
Tercero para asegurarse de que el contenedor se ejecuta correctamente, se utiliza el siguiente comando:
```
docker ps
```
# Evidencia:
<imag
