#Building a module:#

* Abrimos Netbeans, creamos un proyecto php con servidor remoto. Este lo configuramos con nuestra ip y añadimos el usuario root para que tenga permisos de acceso a la carpeta addons de la maquina virtual de Odoo (odoo2016.ova).

* En la ventana de confirmacion unicamente seleccionaremos openacademy este es un modulo por defecto de odoo, asi tendremos un ejemplo ya creado sobre el que trabajar.
La estrutura que tenemos en openacademy vamos a modificarla.

  * Los archivos controllers.py y models.py los sacaremos de sus respectivas carpetas para ponerlos ala altura de init.py. Hecho esto borraremos las carpetas models y controllers con lo que tengan dentro.
  Con los archivos demo.xml y templates.xml haremos lo mismo pero no borramos la carpeta de donde provienen.

* Definir un nuevo modelo de datos denominado “Course” en el módulo(models.py) de openacademy. Cada curso tiene un título y una descripción. Siendo estos obligatorios. Editar el archivo openacademy/models.py para incluir una clase “Course”.
Luego creamos un Course predefinido en el xml de demo, podemos crear varios "Courses" por defecto.
  
