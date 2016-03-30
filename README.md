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

* Search views customizan el campo de búsqueda asociado con el list view. Su elemento raíz es y están compuestos por campos que definen los parámetros de búsqueda.
![**](https://github.com/aquinoacordero/TemaOdoo_Openacademy/blob/master/view_search.PNG)

*  Creamos un modelo nuevo llamado Session en models.py y creamos tambien su form view en openacademy.xml.
![**](https://github.com/aquinoacordero/TemaOdoo_Openacademy/blob/master/model_class_session.PNG)
![**](https://github.com/aquinoacordero/TemaOdoo_Openacademy/blob/master/view_session.PNG)

* Usamos los llamados one2many y many2one para crear "campos relacionales" entre los dos modelos, añadiendo en models.py las lineas necesarias y en openacademy.xml adaptamos las vistas.

 * Cada curso tiene un usuario responsable; el valor del campo es un record del modelo built-in res.users.
 Cada sesión tiene un instructor; el valor del campo es un record del modelo built-in res.partner.
 Cada sesión se relaciona con un curso; el valor del campo es un record del modelo openacademy.course y es necesario.
  * Adaptamos la vista:
    Añadir los campos Many2one relevantes a los modelos.
    Añadirlos en las vistas

* Creamos el fichero partner.xml en la carpeta views, partner.py en la carpeta raiz, añadimos en los datos del openerp el partnet.xml y importamos en parnet en el init. Con esto ya podremos crear herencias, las cuales un objeto nuevo puede "heredar" partes de un modelo ya existente.
 
* crear un campo computado, crea un campo y establece su atributo computado en el nombre de un método . El método computado debería simplemente establecer el valor del campo computado en cada record self.

El valor de un campo computado por lo general depende de los valores de otros campos en el registro computarizada . El ORM espera que el desarrollador especificar esas dependencias en el método de cálculo con el funcion depends().

 * Añadir el porcentaje de asientos cogidos en el modelo sesion.
 * Mostrar el campo en el tree y form views
 * Mostrar los campos como una barra de progreso

* Añadimos advertencias llamadas onChange en el models.py, las cuales nos dirán cuando un valor es inválido
