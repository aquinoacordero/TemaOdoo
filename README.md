#Building a module:#

* Abrimos Netbeans, creamos un proyecto php con servidor remoto. Este lo configuramos con nuestra ip y añadimos el usuario root para que tenga permisos de acceso a la carpeta addons de la maquina virtual de Odoo (odoo2016.ova).

* En la ventana de confirmacion unicamente seleccionaremos openacademy este es un modulo por defecto de odoo, asi tendremos un ejemplo ya creado sobre el que trabajar.
La estrutura que tenemos en openacademy vamos a modificarla.

  * Los archivos controllers.py y models.py los sacaremos de sus respectivas carpetas para ponerlos ala altura de init.py. Hecho esto borraremos las carpetas models y controllers con lo que tengan dentro.
  Con los archivos demo.xml y templates.xml haremos lo mismo pero no borramos la carpeta de donde provienen.
