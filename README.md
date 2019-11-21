# ejemploDAGSS
Proyecto Java EE 7 de ejemplo para DAGSS 2019/20

# ESQUEMA
![Esquema del ejemplo](doc/esquema.jpg?raw=true "Esquema del proyecto JSF + JAX-RS")


# PREVIO

* Instalación de NetBeans JEE (versión 8.2) con Servidor de Aplicaciones GlassFish (versión 4.1.1)
  * _Descarga_: [https://netbeans.org/downloads/8.2/](https://netbeans.org/downloads/8.2/)
  * _Pendiente_: Instalación con Netbeans 11 y Payara 5

* Descargar driver JDBC de MySQL y copiarlo en el directorio de librerias de GlassFish
   ```
   cd /tmp

   wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-8.0.18.zip

   unzip mysql-connector-java-8.0.18.zip

   cp mysql-connector-java-8.0.18/mysql-connector-java-8.0.18.jar \
      $HOME/glassfish-4.1.1/glassfish/domains/domain1/lib/

   pushd
   ```

* Crear BD `pruebas_dagss` en MySQL
   ```
   $ mysql -u root -p    [pedirá la contraseña de MySQL]

   mysql> create user dagss@localhost identified by "dagss";
   mysql> create database pruebas_dagss;
   mysql> grant all privileges on pruebas_dagss.* to dagss@localhost;
   ```

   Adicionalmente, puede ser necesario establecer un formato de fecha compatible
   ```
   mysql> set @@global.time_zone = '+00:00';
   mysql> set @@session.time_zone = '+00:00';
   ```  

* Descargar copia del proyecto desde GitHub
   ```
   git clone https://github.com/dagss2019/ejemploDAGSS.git
   ```

# DOCUMENTACION
* [Creación del proyecto con Netbeans paso a paso](/doc/pasos_netbeans.md)

# TAREAS FUTURAS
1. Descargar, ejecutar e inspeccionar el proyecto
2. Añadir las vistas para la visualización y gestión de los anuncios 
3. Añadir un API REST empleando JAX-RS
