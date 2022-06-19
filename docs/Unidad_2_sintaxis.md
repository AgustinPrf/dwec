##**<u><span style="color:blue">1.- INTRODUCCIÓN</span> </u>**
Javascript es un lenguaje de programación que permite ejecutar código en el cliente (*nuestro navegador*) ampliando la funcionalidad nuestros sitios web. Para añadir JavaScript se usa la etiqueta **script**.
Este puede estar en cualquier lugar de la página. El código se ejecuta de forma secuencial a como el navegador lo va encontrando.

~~~javascript
	<SCRIPT LANGUAGE="JavaScript">
	<!--
		Aquí va el código
		// Esto es un comentario en Javascript de una linea
	-->
	</SCRIPT>
~~~

##**<u><span style="color:blue">2.- Comentarios</span> </u>**
En Javascript los comentarios se pueden hacer con:

* //  	→  *Comentarios de una línea.*
* /\* \*/ →  *Comentarios de varias líneas.*

Desde Javascript es posible reescribir el código HTML de la página mediante la orden 

<center>**document.write(*texto*)**</center>

Este ejemplo podría ser un pequeño *"hola mundo"* que al ejecutarse modificará el HTML de la página.
~~~javascript
	<SCRIPT LANGUAGE="JavaScript">

		document.write ("Hola mundo");
		/* 
			Esto es un comentario 
			en Javascript multilinea 
		*/	
	</SCRIPT>
~~~
Otra vía para mostrar información al usuario desde una ventana emergente, es el comando **alert(*texto*).**
~~~javascript
	<SCRIPT LANGUAGE="JavaScript">
	
		alert("Hola mundo");
	
	</SCRIPT>
~~~
Hay una forma mucho más práctica y ordenada de usar código Javascript. Se pueden incluir uno o varios ficheros con código Javascript. Se pueden incluir tantos como se desee. Un ejemplo de inclusión de ficheros.
~~~javascript
	<script type="text/javascript" src="rutaDelArchivo1.js"/>
	<script type="text/javascript" src="rutaDelArchivo2.js"/>
	<script type="text/javascript" src="rutaDelArchivo3.js"/>
~~~
##**<u><span style="color:blue">3. Variables </span> </u>**

Las variables son elementos del lenguaje que permiten almacenar distintos valores en cada momento. Se puede almacenar un valor en una variable y consultar este valor posteriormente. También podemos modificar su contenido siempre que queramos.
Para declarar las variables en JavaScript se utiliza la palabra reservada **var**.
~~~javascript
	var ejemplo;
	var resultado;
	ejemplo= "Hola";
	resultado=3+7;
~~~
En JavaScript todas las variables y nombres de función son *sensibles a mayúsculas y minúsculas*. Esto significa que la capitalización importa. Escribe los nombres de las variables en JavaScript en **camelCase**. En camelCase, los nombres de variables de múltiples palabras tienen la primera palabra en minúsculas y la primera letra de cada palabra posterior en mayúsculas.

###  **Tipos de variables**
JavaScript proporciona ocho tipos de datos diferentes:

* **undefined**, null, boolean, string, symbol, bigint, number, y object.
* **Números**, puede contener cualquier tipo de número real (0.3,1.7,2.9) o entero (5,3,-1).
* **Operadores, lógicos o boolean**: puede contener uno de los siguientes valores: true, false, 1 y 0.
* **Cadenas de caracteres o String**, cualquier combinación de caracteres (letras, números, signos especiales y espacios). Las cadenas se delimitan mediante comillas dobles o simples (“Lolo”,”lalO”). Para concatenar cadenas puede usarse el operador +  (“Soy” + “ el “ + “ AMO” formaría la cadena “Soy el AMO”).
* **Undefined**: Valor no definido, es decir, la variable no tiene asignado un valor.

~~~javascript
	var edad=23, nueva_edad, incremento;
	var nombre="Rosa García";
	incremento=4;
	nueva_edad=edad+incremento;
	alert(nombre+ " dentro de "+incremento +" años tendrá "+ nueva_edad+"años");
~~~
Puedes utilizar la función **typeof** para consultar el tipo de la variable o dato:
~~~javascript
	console.log(typeof(5))
~~~
 ###  **Arrays**
Un array (también llamado vector o arreglo) es una variable que contiene diversos valores. Lo creamos con “new Array()” o inicializando los elementos. Podemos referenciar esos valores indicando su posición en el array. Los arrays poseen una propiedad llamada “length” que podemos utilizar para conocer el número de elementos del array.

~~~javascript
					// Array definido 1 a 1
	var miVector=new Array();
	miVector[0]=22;
	miVector[1]=12;
	miVector[2]=33;
					//Array definido en una linea
	var otroArray=[1,2,"Cancamusa"];
					// Valores dentro del array
	alert(miVector[1]);
	alert(otroArray[2]);
					// Valor completo del array
	alert(miVector);
					// Tamaño del array
	alert(miVector.length);
~~~

 ###  **Conversiones entre tipos**
Javascript no define explícitamente el tipo de datos de sus variables. Según se almacenen, pueden ser cadenas (Entrecomillados), enteros (sin parte decimal) o decimales (con parte decimal).
Elementos como la función “prompt” para leer de teclado, leen los elementos siempre como cadena. Para estos casos y otros, merece la pena usar funciones de conversión de datos.
~~~javascript
	var num=”100”; 		// Es una cadena
	var num2=”100.13”; 		// Es una cadena
	var num3=11; 			// Es un entero
	var n=parseInt(num); 		// Almacena un entero. 
	var n2=parseFloat(num); 	// Almacena un decimal
	var n3=num3.toString(); 	// Almacena una cadena
~~~
##**<u><span style="color:blue">4. Mostrar por pantalla y leer del teclado</span> </u>**
### **alert() , confirm(), prompt()**
El método **alert()** permite mostrar al usuario información literal o el contenido de variables en una ventana independiente. La ventana contendrá la información a mostrar y el botón aceptar.

<center>
~~~
alert("Bienvenido Agustín");
~~~
</center>

A través del método **confirm()** se activa un cuadro de diálogo que contiene los botones Aceptar y Cancelar.
* **True**  → Se ha pulsado la opción aceptar (botón).
* **False** → Se ha pulsado la opción cancelar (botón). 
  

Con ayuda de este método el usuario puede decidir sobre preguntas concretas e influir de ese modo directamente en la página.

~~~javascript
	var respuesta;
	respuesta=confirm ("¿Desea cancelar la subscripción?");
	alert("Usted ha contestado que "+respuesta);
~~~

El método *prompt()* abre un cuadro de diálogo en pantalla en el que se pide al usuario que introduzca algún dato. Si se pulsa el botón Cancelar, el valor de devolución es false/null. Pulsando en Aceptar se obtiene el valor true y la cadena de caracteres introducida se guarda para su posterior procesamiento.

~~~
	var provincia;
	provincia=prompt("Introduzca la provincia ","Granada");
	alert("Usted ha introducido la siguiente información "+provincia)
~~~

### **Template Literals**
Desde ES2015 también podemos poner una cadena entre ` (acento grave) y en ese caso podemos poner dentro variables y expresiones que serán evaluadas al ponerlas dentro de **${}**. También se respetan los saltos de línea, tabuladores, etc que haya dentro.	

~~~javascript
	let edad=40
	console.log(`El usuario tiene: ${edad} años`)
~~~

##**<u><span style="color:blue">5. Operadores</span> </u>**
Combinando variables y valores, se pueden formular expresiones más complejas. Las expresiones son una parte esencial de los programas. Para formular expresiones se utilizan los operadores.

### ** Operadores de asignación**
Los operadores de asignación se utilizan para asignar valores a las variables. Alguno de ellos también incluyen operaciones.

| Operador | Descripción                                                  |
| -------- | ------------------------------------------------------------ |
| =        | Asigna a la variable de la parte izquierda el valor de la parte derecha. |
| +=       | Suma los operandos izquierdo y derecho y asigna el resultado al operando izquierdo. |
| -=       | Resta el operando derecho del operando izquierdo y asigna el resultado al operando izquierdo. |
| *=       | Multiplica ambos operandos y asigna el resultado al operando izquierdo. |
| /=       | Divide ambos operandos y asigna el resultado al operando izquierdo. |
| %=       | Divide ambos operandos y asigna el resto al operando izquierdo. |

~~~javascript
	var num1=3;
	var num2=5;
	num2+=num1;
	num2-=num1;
	num2*=num1;
	num2/=num1;
	num2%=num1;
~~~

### **Operadores aritméticos**
Los operadores aritméticos se utilizan para hacer cálculos aritméticos.

| Operador | Descripción                    |
| -------- | ------------------------------ |
| +        | Sumar                          |
| -        | Restar                         |
| *        | Multiplicar                    |
| /        | Dividir                        |
| %        | Calcular resto de una división |

Además de estos operadores, también existen operadores aritméticos unitarios: incremento (++), disminución (--) y la negación unitaria (-). Los operadores de incremento y disminución pueden estar tanto delante como detrás de una variable. Estos operadores aumentan o disminuyen en 1, respectivamente, el valor de una variable. 

La diferencia entre ambas posiciones reside en el momento en que se ejecuta la operación.

| Operador<br />   (x=5) | Descripción                                                  |
| ---------------------- | ------------------------------------------------------------ |
| y= ++ x                | Primero el incremento y después la asignación.            y=6 |
| y = x++                | Primero la asignación y después el incremento.            y=5 |
| y = -- x               | Primero el decremento y después la asignación.           y=4 |
| y = x--                | Primero la asignación y después el decremento.           y=5 |
| y =-x                  | Se asigna a y el valor negativo de x, pero x no varía.   y=-5 |

~~~javascript
	var num1=5, num2=8,resultado1, resultado2; 
	resultado1=((num1+num2)*200)/100;
	resultado2=resultado1%3;
	resultado1=++num1;
	resultado2=num2++;
	resultado1=--num1;
	resultado2=num2--;
~~~
###  **Operadores de comparación**
Para comparar dos valores entre sí, se utiliza el operador de comparación. Como valor de retorno se obtiene un valor lógico o booleano: true o false. 

| Operador | Descripción                                                  |
| -------- | ------------------------------------------------------------ |
| ==       | Devuelve el valor true cuando los dos operandos son iguales. |
| !=       | Devuelve el valor true cuando los dos operandos son distintos. |
| \>       | Devuelve el valor true cuando el operando de la izquierda es mayor que el de la derecha. |
| <        | Devuelve el valor true cuando el operando de la derecha es menor que el de la izquierda. |
| >=       | Devuelve el valor true cuando el operando de la izquierda es mayor o igual que el de la derecha. |
| <=       | Devuelve el valor true cuando el operando de la derecha es menor o igual que el de la izquierda. |

~~~javascript
	var a=4;b=5;
	alert("El resultado de la expresión 'a==b' es igual a "+(a==b));
	alert("El resultado de la expresión 'a!=b' es igual a "+(a!=b));
	alert("El resultado de la expresión 'a>b' es igual a "+(a>b));
	alert("El resultado de la expresión 'a<b' es igual a "+(a<b));
	alert("El resultado de la expresión 'a>=b' es igual a "+(a>=b));
	alert("El resultado de la expresión 'a<=b' es igual a "+(a<=b));
~~~
### **Operadores lógicos**
Los operadores lógicos se utilizan para el procesamiento de los valores booleanos. A su vez el valor que devuelven también es booleano: true o false.

| Operador | Descripción                                                  |
| -------- | ------------------------------------------------------------ |
| &&       | Y lógica. El valor de devolución es true cuando ambos operandos son verdaderos. |
| \|\|     | O lógica. El valor de devolución es true cuando alguno de los operandos es verdadero o lo son los dos. |
| !        | No lógica. El valor de devolución es true cuando el valor es falso. |


Ejemplo de resultado de distintas operaciones realizadas con operadores lógicos.

~~~javascript
	alert(”resultado 'false&&false' es igual a "+(false&&false));
	alert("resultado 'false&&true' es igual a "+(false&&true));
	alert("resultado 'true&&false' es igual a "+(true&&false));
	alert("resultado 'true&&true' es igual a "+(true&&true));
	alert("resultado 'false||false' es igual a "+(false||false));
	alert(“resultado 'false||true' es igual a "+(false||true));
	alert("resultado 'true||false' es igual a "+(true||false));
	alert("resultado 'true||true' es igual a "+(true||true));
	alert("resultado '!false' es igual a "+(!false));
~~~
## ** <u>6. Estructuras de control y bucles </span> </u>**
### **IF y ELSE**
Para controlar el flujo de información en los programas JavaScript existen una serie de estructuras condicionales y bucles que permiten alterar el orden secuencial de ejecución. La instrucción **if**  permite la ejecución de un bloque u otro de instrucciones en función de una condición.


~~~javascript
	if (condición) {
		// bloque instrucciones,se ejecutan si la condición se cumple
	}
	else{
		// bloque instrucciones, se ejecutan si la condición no se cumple
	}
~~~

Las llaves solo son obligatorias cuando haya varias instrucciones seguidas pertenecientes a la ramificación. 
Si no pones llaves, el if se aplicará únicamente a la siguiente instrucción(primera instrucción).

~~~javascript
	let edadAna,edadLuis;
	edadAna=parseInt(prompt("Introduce la edad de Ana",""));
	edadLuis=parseInt(prompt("Introduce la edad de Luis",""));
	if (edadAna > edadLuis){
		alert("Ana es mayor que Luis.");
		alert(` Ana tiene ${edadAna} años y Luis ${edadAna}`);
	}
	else{
		alert("Ana es menor o de igual edad que Luis.");
		alert(" Ana tiene " + edadAna + " años y Luis " + edadLuis);
	} 
~~~
Para las condiciones ramificadas más complicadas, a menudo se utilizan las ramificaciones anidadas. En ellas se definen consultas if dentro de otras consultas if.
~~~javascript
	var edadAna,edadLuis;
	edadAna=parseInt(prompt("Introduce la edad de Ana",""));
	edadLuis=parseInt(prompt("Introduce la edad de Luis",""));
	if (edadAna > edadLuis){
		alert("Ana es mayor que Luis.");
	}
	else{
		if (edadAna<edadLuis){
			alert("Ana es menor que Luis.");
		}else{
			alert("Ana tiene la misma edad que Luis."); 
		}
	} 
	alert(` Ana tiene ${edadAna} años y Luis ${edadAna}`);
~~~

### **Bucle FOR**
Cuando la ejecución de un programa llega a un bucle for, lo primero que hace es ejecutar la **“inicialización del índice”**, que solo se ejecuta un vez, a continuación analiza la **“condición de prueba”** y si esta se cumple ejecuta las instrucciones del bucle. Cuando finaliza la ejecución de las instrucciones del bucle se realiza la **“modificación del índice”** .
~~~javascript
for (inicialización_índice; condición_prueba; Modificación_índice){
	// Bloque de instrucciones...
}
~~~
Ejemplo: números pares del 2 al 30
~~~javascript
	for (i=2;i<=30;i+=2) {
		alert(i);
	}
	alert(" Ya se han escrito los números pares del 0 al 30");
~~~
 ### **Bucle WHILE**
Con el bucle while se pueden ejecutar un grupo de instrucciones mientras se cumpla una condición. Si la condición nunca se cumple, entonces tampoco se ejecuta ninguna instrucción.

~~~javascript
	while (condición){
		// Bloque de instrucciones...
	}
~~~
Ejemplo : Escribe los números pares de 0 a 30
~~~
	i=2;
	while (i<=30) {
		alert (i);
		i+=2;
	} 
	alert("Ya se han mostrado los números pares del 0 al 30");
~~~

### **Bucle DO-WHILE**
La diferencia del bucle do-while frente al bucle while reside en el momento en que se comprueba la condición: 

* El bucle **do-while** no la comprueba hasta el final. Lo que significa que el bucle do-while se recorrerá, una vez, como mínimo, aunque no se cumpla la condición.

~~~javascript
	do {
		// Bloque de instrucciones...
	} while(condición)
	Ejemplo: Preguntar por una clave hasta que se introduzca la correcta
	do {
		auxclave=prompt("introduce la clave ","vivaYo")
	} while (auxclave!="EstaeslaclaveJEJEJE")

	alert ("Has acertado la clave");
~~~
###  **Instrucciones BREAK y CONTINUE**
En los bucles for, while y do-while se pueden utilizar las instrucciones **break** y **continue** para modificar el comportamiento del bucle. 

* **Break**  → Hace que el bucle se interrumpa inmediatamente, aun cuando no se haya ejecutado todavía el bucle completo.      

Ejemplo: Pregunta por la clave y permitir tres respuestas incorrectas

~~~javascript
var auxclave=true , var numveces=0;
while (auxclave != "anonimo" && auxclave){ 
	auxclave=prompt("Introduce la clave ","");
	numveces++;
	if (numveces == 3)
		break;
}
if (auxclave=="SuperClave") alert("La clave es correcta");
else alert("La clave no es correcta correcta");
~~~

* **Continue**  → Hace retornar a la secuencia de ejecución a la cabecera del bucle, volviendo a ejecutar la condición o a incrementar los índices cuando sea un bucle for. 

Ejemplo: Presenta todos los números pares del 0 al 50 excepto los que sean múltiplos de 3
~~~
	var i;
	for (i=2;i<=50;i+=2){
		if ((i%3)==0) 
			continue;
		alert(i);
	}
~~~

## ** <u>7. Funciones</u> **
Se declaran con la palabra reservada **function** y se les pasan los parámetros entre paréntesis. La función puede devolver un valor usando **return** (*si no tiene return es como si devolviera undefined*).
 ~~~ javascript
	function nombrefuncion (parámetro1, parámetro2...){
	...
		// Bloque de instrucciones
	...
		//si la función devuelve algún valor añadimos:
		return valor;
	}
 ~~~
Ejemplo:Funciones que devuelve la suma de dos valores que se pasan por parámetros y que escriben el nombre del profesor.
~~~javascript
// Definiciones de las funciones
	function suma (a,b){ 
		return a+b;
	}
	function profe (){
		alert ("El profesor es: Agustin Aguilera");
	}
// Código que se ejecuta
	let op1=5;op2=25;
	let resultado;
// Llamadas a funciones
	resultado=suma(op1,op2); 
	console.log (op1+"+"+op2+"="+resultado);	
	profe();
~~~

### **Uso del array arguments**
También es posible acceder a los parámetros desde el **array arguments[]** si no sabemos cuántos recibiremos:

~~~javascript
	function suma () {
    		var result = 0;
    		for (var i=0; i<arguments.length; i++)
        		result += arguments[i];
	 	return result;
	}
~~~

### **Uso de funciones anónimas**
Podemos definir una función sin darle un nombre. Dicha función puede asignarse a una variable, autoejecutarse o asignarse a un manejador de eventos. 
~~~javascript
	var suma = function (a,b){ 
		return a+b;
	}
~~~

###  **funciones lambda o funciones flecha**
Para escribir la sintaxis de una función flecha, debemos tener en <u>**consideración**</u>:

* Eliminamos la palabra function 
* Ponemos el símbolo => 
* Si sólo tiene 1 parámetro podemos eliminar los paréntesis de los parámetros 
* Si la función sólo tiene 1 línea podemos eliminar las { } y la palabra return         

```javascript
 // Función anónima
 var suma = function (a,b){ 
	return a+b;
}
 // Función flecha   
  var suma = (a,b) => {return a+ b}
  var suma = (a,b) =>  a+ b
```


## ** <u>8. Variables locales y globales</u> **

 Ahora que ya conocemos las funciones es muy importante diferenciar entre variables globales y locales:

* **Variables globales** →  Pueden utilizarse en cualquier parte del código y son declaradas fuera de toda función.
* **Variables locales** →  Se definen con la instrucción **let** dentro de una función y solo pueden ser utilizadas dentro de esta.

~~~javascript
	var v_global1=20;
	
	function prueba(){
		let v_local1=10; //Definición de variable local
		let v_local2=v_global1+v_local1;
		//En la función se puede acceder a las variables globales 
		// y locales definidas dentro de ella
		alert ("Suma de v. local y la global : "+ v_local2);
	}
	prueba();
	
	alert ("La variable global es "+vbleglobal1);
	//Desde fuera de la función las variables locales definidas en ella no son accesibles
~~~

