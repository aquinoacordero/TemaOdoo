#Building a module:#

* Abrimos Netbeans, creamos un proyecto php con servidor remoto. Este lo configuramos con nuestra ip y añadimos el usuario root para que tenga permisos de acceso a la carpeta addons de la maquina virtual de Odoo (odoo2016.ova).

* En la ventana de confirmacion unicamente seleccionaremos openacademy este es un modulo por defecto de odoo, asi tendremos un ejemplo ya creado sobre el que trabajar.
La estrutura que tenemos en openacademy vamos a modificarla.

  * Los archivos controllers.py y models.py los sacaremos de sus respectivas carpetas para ponerlos ala altura de init.py. Hecho esto borraremos las carpetas models y controllers con lo que tengan dentro.
  Con los archivos demo.xml y templates.xml haremos lo mismo pero no borramos la carpeta de donde provienen.

* Definir un nuevo modelo de datos denominado “Course” en el módulo(models.py) de openacademy. Cada curso tiene un título y una descripción. Siendo estos obligatorios. Editar el archivo openacademy/models.py para incluir una clase “Course”.
Luego creamos un Course predefinido en el xml de demo, podemos crear varios "Courses" por defecto.
 ![**](https://github.com/aquinoacordero/TemaOdoo_Openacademy/blob/master/course_demo.PNG)

* En el openacademy.xml creamos un menú de Courses, con el cual un usuario podrá modificar o crear sus propios Cursos. 
 * Mostrar una lista de todos los cursos.
 * Crear o Modificar cursos.

* Configuramos nuestro openacademy.xml para que salga nuestro menú de Course a nuestro gusto, Para ello se emplea un "Form view".
 * Una vista (view) se declara como un record del módelo ir.ui.view. El tipo de vista viene indicado por el campo arch
   Tree views el cual muestran los records en una tabla. El elemento raíz es "<"tree">".
   Forms son usados para crear y editar records. Su elemento raiz es "<"form">".
