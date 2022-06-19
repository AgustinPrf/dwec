##**<u><span style="color:blue">1.- FORMULARIOS </span> </u>**
En esta unidad trataremos algunas de las operaciones más habituales en los formularios. En primer lugar veremos la estructura genérica de un formulario, para a continuación afrontar las operaciones de modificar apariencia, comportamiento, validación,etc.

Un formulario web sirve para enviar, tratar y recuperar datos que son enviados y recibidos entre un cliente y un servidor web. Cada elemento del formulario almacena un tipo de dato o acciona una de sus funcionalidades. Los formularios disponen de una arquitectura, en este contexto están enmarcados en el lenguaje HTML.

**Aclaración** Al hacer una aplicación Web, el cliente debe validar la información introducida, pero ello no quita el servidor también deba validarla.

### **Estructura de un formulario**

Desde un punto de vista general, los formularios presentan la estructura:

* Los formularios se definen con etiquetas. Dentro de cada etiqueta también podemos acceder a los atributos de la misma.
* La etiqueta principal es "form". Para que sea funcional, la etiqueta "form" necesita inicializar dos atributos:
	* **action** → Contiene la URL donde se redirigen los datos del formulario.
	* **method** → Indica el método por el cual el formulario envía los datos. Puede ser POST o GET.
	
* **Además** de los atributos principales anteriores, podemos encontrar otros atributos como:
	* **enctype** → define el tipo de codificación para enviar el formulario al servidor. Se usa cuando permite enviar archivos adjuntos.
	* **accept** → indica el tipo de fichero adjunto que acepta el servidor.

~~~javascript

	<body>
		<h3>Formulario</h3>
		<form action="www.Web.es/formulario.php" method="post">
			...
		</form>
	</body>
~~~

### **Elementos de un formulario**

El elemento principal del formulario se denomina con la etiqueta "input". Según su funcionalidad, los tipos de input se llaman:

* **Controles de formulario** → Botones, etc…
* **Campos de formulario** → Contienen los datos que se envían a través del formulario.

En una etiqueta input podemos encontrar los atributos:

* **Type** → Indica el tipo de elemento que vamos a definir. De él dependen el resto de parámetros. Los valores posibles que acepta el atributo type son:
	* **text** → Cuadro de texto.
	* **password** → Contraseña.
	* **checkbox** → Casilla de verificación.
	* **radio** → Opción de entre dos o más.
	* **submit** → Botón de envío del formulario.
	* **reset** → Botón de vaciado de campos.
	* **file** → Botón para buscar ficheros.
	* **Hidden** → Campo oculto para, el usuario no lo visualiza en el formulario.
	* **Image** → Botón de imagen.

* **Name** → El atributo name asigna un nombre al elemento. Si no le asignamos nombre a un elemento, el servidor no podrá identificarlo y por tanto no podrá tener acceso al elemento.
	
* **Value** → El atributo value inicializa el valor del elemento. Los valores dependerán del tipo de dato, en ocasiones los posibles valores a tomar serán verdadero o falso.
	
* **Size** → Este atributo asigna el tamaño inicial del elemento. El tamaño se indica en pixeles. En los campos text y password hace referencia al número de caracteres.
	
* **Maxlength** → Este atributo indica el número máximo de caracteres que pueden contener los elementos text y password. Es conveniente saber que el tamaño de los campos text y password es independiente del número de caracteres que acepta el campo.

* **Checked** → Este atributo es exclusivo de los elementos checkbox y radio. En el definimos que opción por defecto queremos seleccionar.

* **Disable** → Este atributo hace que el elemento aparezca deshabilitado. En este caso el dato no se envía al servidor.

* **Readonly** → Este atributo sirve para bloquear el contenido del control, por tanto el valor del elemento no se podrá modificar.

* **src** → Este atributo es exclusivo para asignar una URL a una imagen que ha sido establecida como botón del formulario.

* **Alt** → El atributo alt, incluye una pequeña descripción del elemento. Habitualmente y si no lo hemos desactivado cuando posicionamos el ratón (sin pulsar ningún botón) encima del elemento, podemos visualizar la descripción del mismo.

### **Tipos de input**

* **Cuadro de texto:**
Este input muestra un cuadro de texto vacío en el que el usuario puede introducir un texto. Este es uno de los elementos más usados. La forma de indicar que es un campo de texto es:

~~~javascript
<input type="text
~~~

* **Cuadro de contraseña:**
El cuadro de contraseña es como el cuadro de texto, con la diferencia que los caracteres que escribe el usuario no se ven en pantalla. En su lugar los navegadores muestran asteriscos o puntos:

~~~javascript
<input type="password" name="contrasenia" />
~~~

* **Casilla de verificación**

Estos elementos permiten al usuario actilet o desactilet la selección de cada una de las casillas de forma individual.

~~~javascript
	<p>Colores favoritos</p>
	</br><input name="rojo" type="checkbox" value="ro"/> Rojo
	</br><input name="azul" type="checkbox" value="az"/> Azul
	</br><input name="verde" type="checkbox" value="ve"/> Verde
~~~

* **Opción de radio**
Este tipo de elemento agrupa una serie de opciones excluyentes entre sí. De esta forma el usuario sólo puede coger una opción de entre todas las que tiene establecidas un grupo de botones radio.

~~~javascript
	Género
	</br><input type="radio" name="género" value="M"> Hombre
	</br><input type="radio" name="género" value="F"> Mujer
~~~

* **Botón de envío**
 Este elemento es el encargado de enviar los datos del formulario al servidor. En este caso el type toma el valor submit. El valor del atributo value se mostrará en este caso en el botón generado.

~~~javascript
<input type="submit" name="enviar" value="Enviar">
~~~

* **Botón de reset:**
Este elemento es un botón que establece el formulario a su estado original.

* **Ficheros adjuntos:**
Este tipo de input permite adjuntar ficheros adjuntos. El elemento añade de forma automática un cuadro de texto que se dispondrá para almacenar la dirección del fichero adjunto seleccionado.

~~~javascript
Fichero adjunto
<input type="file" name="fichero"/>c
<form action="" method="post" enctype="multipart/formdata"> ... </form>
~~~

* **Campos ocultos**
Los campos ocultos no son visibles en el formulario por el usuario. Estos elementos son útiles para enviar información de forma oculta que no tenga que ser tratada por el usuario.

~~~javascript
	<input type="hidden" name="campoOculto" value="cambiar"/>
~~~
* **Botón de imagen:**
Este elemento es una personalización de un botón, cambiando el aspecto por defecto que tienen los botones de un formulario por una imagen.

~~~javascript
<input type="image" name="enviar" src="imagen_mundo.jpg"/>
~~~

**Botón**:
Existe un elemento botón, al que podemos asociar diferentes funcionalidades. De esta forma no nos tenemos que ceñir los botones de submit o reset que nos ofrecen los formularios.

~~~javascript
<input type="button" name="opcion" value="Opcion validar"/>
~~~

* Ejemplo completo
~~~javascript
<form action="pagina.php" method="post"
	enctype="multipart/form-data" /> <br/>
	
	Nombre:
	<input type="text" name= "nombre" value="" size="42 maxlength="30"/>

	Apellidos:
	<input type="text" name="ape" value="" size="40" maxlength="80"/>

	DNI:
	<input type="text" name="dni" value="" size="10" maxlength="9" />

	Sexo:
	<input type="radio" name="sexo" value="hombre" checked="checked"/>Hombre
	<input type="radio" name="sexo" value="mujer" />Mujer
	
	Incluir mi foto:
	<input type="file" name="foto" /> <br/>
	<input name="publ" type="checkbox" value="publicidad" checked="checked"/>
	
	Enviar publicidad
	<input type="submit" name="enviar" value="Guardar cambios" />
	<input type="reset" name="limpiar" value="Borrar los datos introducidos"/>
</form>
~~~
##**<u><span style="color:blue">2.- ACCEDER A ELEMENTOS DE FORMULARIOS </span> </u>**

### **text**
Para acceder al valor de un input de tipo texto, simplemente debemos referenciar el atributo "value".
~~~javascript
	<input type="text" id="miTexto">
	let elemento=document.getElementById("miTexto");
	alert(elemento.value);
~~~

### **Radio button**
Radio button son elementos del formulario, que ante varias entradas, te dejan seleccionar una de ellas. Se agrupan teniendo un "name" común.
Para acceder a ellos, se accede como un array, donde se tiene el atributo "value" y el atributo "checked" que es true si está seleccionado, false en caso contrario.

~~~javascript
	<input type="radio" id="preguntaSI" name="pregunta" value="si" />SI
	<input type="radio" id="preguntaNO" name="pregunta" value="no" />NO

	let elementos=document.getElementsByName("pregunta");
	for(i=0;i<elementos.length;i++){
		if(elementos[i].checked==true)
			alert("Valor del elemento marcado "+elementos[i].value);
}
~~~
### **checkbox**
Similar a los radio button, salvo que puede haber más de uno marcado.

~~~javascript
	<input type="checkbox" id="preguntaAS" name="pregunta" value="asc" />Piso con ascensor
	<input type="radio" id="preguntaAM" name="pregunta" value="amb" />Piso amueblado

	let elementos=document.getElementsByName("pregunta");

	for(i=0;i<elementos.length;i++){
		if(elementos[i].checked==true){
			alert("Valor del elemento marcado "+elementos[i].value);
		}
	}

~~~

### **select**

Elemento que muestra un desplegable y nos permite elegir una opción del mismo. Aquí destaca el atributo "options", que es un atributo que contiene un array con las opciones disponibles y el atributo "selectedIndex"
que contiene (y se puede modificar) la posición del array "options" seleccionada actualmente (o la primera si se permite multiselección) o -1 si no está seleccionada ninguna opción (o queremos des-seleccionarlas).
Dentro de cada "options", "value" almacena el valor y "text" el texto mostrado.
~~~javascript
	<select id="aprobar" >
		<option value="10">Saco 10 en DWEC</option>
		<option value="9">Saco 9 en DWEC</option>
		<option value="8">Saco 8 en DWEC</option>
	</select>

	let elemento=document.getElementById("aprobar");
	
	for(i=0;i<elemento.options.length;i++){
		alert("Valor de la opcion "+elemento.options[i].value);
	}

	let sel=elemento.selectedIndex;
	alert("El valor de la opcion seleccionada es "+elemento.options[sel].value+" y el texto asociado es "+elemento.options[sel].text);
	
	// Cambiamos el indice seleccionado
	elemento.selectedIndex=0
~~~


##**<u><span style="color:blue">3.- VALIDACIÓN Y ENVÍO DE FORMULARIOS </span> </u>**

El usuario puede cometer errores al rellenar un formulario. Si por ejemplo se espera un código postal y se introduce el nombre de una ciudad, se producirá un error. Para controlar estas situaciones se pueden usar las validaciones. Este tipo de validaciones se suelen realizar llamando a una función que analice si el dato cumple con las restricciones establecidas.

### **Validar un formulario**

 Si un manejador de un evento devuelve true ( o no devuelve nada ) , se realiza el evento asociado. Si el manejador devuelve false, se cancela el evento. Existe un evento asociado a un formulario completo llamado "onsubmit".
Aprovechando esto, podemos a nuestro antojo permitir el envió de información al servidor mediante el formulario devolviendo true o cancelarlo devolviendo false.
La estructura típica es la siguiente:
~~~javascript
	<form onsubmit="return validarFecha();">
~~~javascript
Si la función validar devuelve true, se realiza el envío. Si devuelve false, se cancela.
En la función validar podemos hacer las validaciones que estimemos convenientes. Es decir, para crear funciones de validación, se debe devolver un booleano:
* true → Sí se lanza el evento "submit"
* false → No se lanza el evento "submit"

~~~javascript
script type="text/javascript">
	function validaFecha() {
		let dia = document.getElementById("dia").value;
		let mes = document.getElementById("mes").value;
		let ano = document.getElementById("ano").value;

		fecha = new Date(ano, mes, dia);
	
		if( !isNaN(fecha) ) {
	
			return false;
		}
	
		return true;
	}
 	
	<form action="" onsubmit="return validacion()" method="" id="" name="" >
	 ...
	 </form>
 <script>

 function validacion(){
	valor=document.getElementById("label1").value;
	if (!isNaN(valor)){
		console.log(valor);
	 	return true;
	}
	
	return false;
}
</script>
~~~

### **Deshabilitar enviar un formulario dos veces**

A veces un usuario pulsa enviar un formulario mas de una vez por error. Si queremos evitar esto, podemos usar la propiedad "disabled";

~~~javascript
	document.getElementById("idSubmit").disabled = true;
~~~

### **Enviar un formulario desde código**
En algunas aplicaciones por motivos estéticos o de funcionalidad es deseable que el "enviar un formulario" no se haga desde un botón "submit", sino desde cualquier otro evento que permita la ejecución de código. Esto se
puede hacer recogiendo el elemento del formulario y aplicándole el método submit();

~~~javascript
	let elemento=document.getElementById("formulario");
	elemento.submit();
~~~

##**<u><span style="color:blue">4.- ACCESO A RESTRICCIONES DE HTML </span> </u>**
Mediante Javscript tenemos acceso a todos los campos del formulario por lo que podemos hacer la validación como queramos, pero es una tarea pesada, repetitiva y que provoca código spaguetti difícil de leer y mantener más adelante.
Para hacerla más simple podemos usar la API de validación de formularios de HTML5:

Esta API nos proporciona estas propiedades y métodos:

* **checkValidity**() → método que nos dice si el campo al que se aplica es o no válido. También se puede aplicar al formulario para saber si es válido o no

* **validationMessage** → en caso de que un campo no sea válido esta propiedad contiene el texto del error de validación proporcionado por el navegador

* **validity** → es un objeto que tiene propiedades booleanas para saber qué requisito del campo es el que falla:
	* **valueMissing**: indica si no se cumple la restricción required (es decir, valdrá true si el campo tiene el atributo required pero no se ha introducido nada en él)
	* **typeMismatch**: indica si el contenido del campo no cumple con su atributo type (ej. type="email")
	* **patternMismatch**: indica si no se cumple con el pattern indicado
	* **tooShort** / **tooLong**: indica si no se cumple el atributo minlength/maxlength
	* **rangeUnderflow** / **rangeOverflow**: indica si no se cumple el atributo min / max
	* **stepMismatch**: indica si no se cumple el atributo step del campo
	* **customError**: indica al campo se le ha puesto un error personalizado con setCustomValidity
	* **valid**: indica si es campo es válido
	* .....
* **setCustomValidity**(*mensaje*) → añade un error personalizado al campo (que ahora ya NO será válido) con el mensaje pasado como parámetro. Nos permite personalizar el mensaje del navegador.
Para quitar este error se hace setCustomValidity('')


##**<u><span style="color:blue">5.- EXPRESIONES REGULARES </span> </u>**

### **Constructores**

| new RegExp(expr, flags) | ***Crea una nueva expresión regular a partir de r con los flags indicados.*** |
| ----------------------- | ------------------------------------------------------------ |
| **/ expr / flags**      | ***Simplemente, la expresión regular r entre barras /. Notación preferida.*** |




~~~javascript
	// DEFINICIÓN COMO LITERAL
	let r = /expr/flag
	let r = /^a/g;
	
	// DEFINICIÓN COMO OBJETO
	let r = new RegExp(expr , flag)
	let r = new RegExp(‘/^a’, ‘g’)
	
	-------------------------------------------------
		r.test(‘cadena_a_comprobar’)
	-------------------------------------------------
	
	let reg_exp = /^\d{8}[a-zA-Z]$/; // 8 cifras numéricas + carácter alfabético.
	if(reg_exp .test(formulario.dni.value)==false) {
		// indicar el error
	}
~~~

### **Flags**
| flag |    flag     |                 Descripción                                 |
| :--: | :---------: | ----------------------------------------------------------: |
|  i   | .ignoreCase |   Ignorar mayúsculas y minúsculas                           |
|  g   |   .global   |   Búsqueda global, no se para al encontrar 1º ocurrencia    |
|  m   | .multiline  |   permite a ^ $ tratar los finales de linea \n              |
|  u   |  .unicode   |   La codificación es unicode                                |
|  y   |   .sticky   |   Busca solo desde la posición indicada                     |


### **Reglas**
| Regla |                                                  Descripción |
| :---: | -----------------------------------------------------------: |
|   ^   |                  Principio            /^ag/→ comienza por ag |
|   $   | Final                                                                                                                  /$in/→ termina en in |
|  []   | Conjunto                                                                                                                       /[a-z]/ /[aeiou]/ |
|  [^]  | Conjunto negado                                        No exista cualquiera de los caracteres entre corchetes |
|  {x}  | Cuantificadores                 /d{4,7}/→ de 4 a 7 dígitos /d{4}/ → 4 dígitos /d{4,}/ → mas de 4 dígitos |
|  \|   | Alternancia                                                                                                                                     /a\|b/→ El valor a ó b |
|   .   |                   Cualquier carácter menos el salto de línea |
|   ?   | Cero o ninguna ocurrencia                                                                                                                        {0,1} |
|   *   | Cero o más ocurrencias                                                                                                                           {0,} |
|   +   | Una o mas ocurrencias                                                                                                                            {1,} |
|  \d   | Dígito                                                                                                                                       [0-9] |
|  \w   | Caracter                                                                                                                         [a-zA-Z0-9] |
|  \s   |                                            Espacio en blanco |



~~~javascript
	const r = /.a.o/i;
	r.test("gato"); 		// true
	r.test("pato"); 		// true
	r.test("perro"); 		// false
	r.test("DATO"); 		// true (el flag i permite mayús/minús)
~~~
