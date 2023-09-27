# Práctica Inicial

### Daniel Marín López

1. Actividad 1: XAMP
2. Actividad 2: VirtualBox
3. Actividad 3: Programa de Java
4. Actividad 4: Vagrant

### Actividad 1: XAMP

Para está práctica partimos de que XAMP ya está instalado y preparado para funcionar.

![captura 1](capturas/xamp.png)

Con XAMP funcionando entramos en nuestro localhost y ponemos nuestro porfolio en htdocs y ya estaría listo en el servidor.

![captura 2](capturas/xamp_porfolio.png)

### Actividad 2: VirtualBox

Para está actividad creamos una máquina virtual con Ubuntu Server.

![captura 3](capturas/server.png)

Una vez terminada la instalación; instalaremos apache, php, mariadb y phpmyadmin.

![captura 5](capturas/apache.png)

![captura 6](capturas/apache2.png)

![captura 7](capturas/php.png)

![captura 8](capturas/php_paquete.png)

![captura 9](capturas/mariadb.png)

![captura 10](capturas/phpmyadmin.png)

![captura 11](capturas/phpmyadmin_paquete.png)

Una vez instalados todos los programas/servicios, instalaremos un plugin en Visual Studio Code para conectarnos mediante ssh.

![captura 12](capturas/plugin.png)

Luego ejecutaremos el siguiente comando:

![captura 13](capturas/conexion.png)

Lo siguiente es poner el `usuario@ipservidor`, luego nos pedirá nuestra contraseña y entraremos (hay que tener buena conexión a internet para que funcione).

![captura 14](capturas/conexion_VS.png)

Una vez cargado, al entrar en cada carpeta pedirá la contraseña.

![captura 15](capturas/vscode1.png)

Para poder hacer modificaciones en `/var/www/html/` hay que tener permisos especiales:

![captura 16](capturas/permisos.png)

Una vez cambiados los permisos, pasamos a crear el porfolio.

![captura 17](capturas/codigo.png)

La foto se puede agregar simplemente arrastrándola al directorio en el Visual Studio Code.

El resultado es el siguiente:

![captura 18](capturas/porfolio.png)

### Actividad 3: Programa de Java

Para esta actividad necesitaremos el programa Eclipse en su versión Enterprise.

![captura 19](capturas/eclipse1.png)

Primero instalaremos el servidor Apache Tomcat a través de Eclipse (también se puede descargar por separado), en nuestro caso instalaremos la versión 7.0.

![captura 20](capturas/eclipse2.png)

Luego crearemos un proyecto dinámico (único en la versión Enterprise) para desarrollar el programa en Java.

![captura 21](capturas/eclipse3.png)

Primero creamos un archivo JSP simple, un Hola Mundo, sin embargo a veces puede que el servidor no arranque porque alguno de sus puertos está en el 8080 y este ya está ocupado (como me ocurrió). Si damos en la opción “Open” en el servidor veremos las configuraciones, mi caso era que el puerto HTTP estaba en el 8080 así que lo cambie al 8081.

![captura 22](capturas/eclipse4.png)

Luego del cambio, el error se solucionó mostrando el Hola Mundo.

![captura 23](capturas/eclipse5.png)

Tras la prueba, nos ponemos a trabajar en el programa. Lo primero que hacemos es crear la página principal index.jsp. En ella se le pedirá al usuario un número en un formulario y devolverá el doble.

![captura 24](capturas/eclipse8.png)

Luego tras terminar la página principal, nos ponemos a trabajar en el programa que necesitará (llamado dobleNServlet.java).

![captura 25](capturas/eclipse7.png)

Una vez finalizado el programa, lo probamos y vemos que funciona correctamente.

![captura 26](capturas/eclipse6.png)

### Actividad 4: Vagrant

Esta práctica consistirá en usar el programa **Vagrant** para crear un proyecto con **Laravel/Homestead**.

Lo primero que hacemos es instalar Vagrant.

![captura 27](capturas/vagrant.png)

![captura 28](capturas/vagrant2.png)

Luego ejecutamos el comando `vagrant box add laravel/homestead` para instalar el proyecto de laravel y seleccionamos la **opción de virtualbox**. En mi caso tuve que añadir `--insecure` por problemas con los certificados SSL.

![captura 29](capturas/vagrant3.png)

Luego clonamos su repositorio con `git clone` el repositorio de laravel.

![captura 30](capturas/vagrant4.png)

Previamente creamos el archivo **id_rsa** para **Homestead.yaml** con el comando `ssh-keygen -t rsa -C "correo@correo.es"`.

![captura 31](capturas/id_rsa.png)

Luego iniciamos Homestead con `init.bat`.

![captura 32](capturas/vagrant5.png)

Modificamos **Homestead.yaml** para incluir el archivo `id_rsa`.

![captura 33](capturas/vagrant6.png)

Con el comando `vagrant up` iniciamos la máquina.

![captura 34](capturas/vagrant7.png)

Con `vagrant ssh` nos conectamos a la máquina de Vagrant.

![captura 35](capturas/vagrant8.png)

Y en el archivo **hosts** añadimos con la IP de **Homestead.yaml** a **homestead.test**.

![captura 36](capturas/vagrant9.png)

Creamos el **index.html** y lo visualizamos en el navegador con **homestead.test**.

![captura 37](capturas/vagrant10.png)

![captura 38](capturas/vagrant11.png)

![captura 39](capturas/vagrant12.png)