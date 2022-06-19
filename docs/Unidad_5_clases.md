##**<u style="color:#2980B9">1. INTRODUCCIÓN</u>**
Javascript es un lenguaje que permite el uso de objetos. Muchas veces el término clase y objeto se confunden. Una definición podría ser que una clase define "como es un objeto" y que un objeto es la plasmación efectiva de ese objeto. A partir de una clase se pueden crear si se desea muchos objetos.
Para entenderlo un <u>***ejemplo*</u>**:

*Supongamos tenemos la clase "casa". Esa clase define que atributos tiene una casa. Un ejemplo de esos atributos podría ser: dirección, numero habitaciones, metros cuadrados. Ahora bien, cada objeto es una casa existente. Podemos tener por ejemplo dos objetos que surgen a partir de la clase "casa". Uno seria una casa con dirección "Avenida del puerto 1, Valencia", 3 habitaciones y 100m2 y otro una casa con dirección "Calle Colón 1, Valencia", 5 habitaciones y 200m2.*

La clase definía como podían ser los objetos y los objetos en si son clases contextualizadas en algo concreto."
##**<u style="color:#2980B9">2. FUNCIONES</u>**
Hay varias formas de crear funciones en Javascript:
• Por **declaración** o por **expresión**( anónima, lambda ) o **flecha**( Ecmas6 ):

|              Definición               |                Descripción                |
| :-----------------------------------: | :---------------------------------------: |
|  function nombre ( p_1,p_2.... ) { }  | Crea una función mediante **declaración** |
| nombre = function ( p_1,p_2.... ) { } |  Crea una función mediante **expresión**  |
|          Nombre = () => { };          |   Crea una función mediante **flecha**    |

<u>**Aclaración</u>** *: Funciones flecha es igual a funciones por expresión pero sin usar la palabra reservada function.*


##**<u style="color:#2980B9">3.- DEFINIR CLASES Y OBJETOS</u>**

###**<span style="color:#2980B9">Funciones constructoras/span>**
La forma de definir clases en Javascript es ligeramente distinta a la utilizada en otros lenguajes de
programación. Aquí la forma de definir una clase y su constructor asociado es simplemente definir una
función.

```javascript
/ ***** Definir la Clase **********/
function PersonaF(nombre, edad){
							// Propiedades	
    this.nombre = nombre;	
	this.edad = edad;
    
							// Métodos
	this.cumplirAnos = function (incremento){
		this.edad=this.edad + incremento;
	};

}
/ ***** Instanciar la Clase ******/
let agustin = new PersonaF("Agustin",36);
agustin.cumplirAnos(1);
console.log(`Nombre: ${agustin.nombre} y edad : ${agustin.edad}`);

```
##**<span style="color:#2980B9">Objeto Json</span>**
Un objeto JSON está rodeado de llaves {}. Siendo su estructura especificada como pares clave / valor.

```javascript
ana = {
    												// Propiedades
		nombre: "Ana Maria",   
		edad: 40,
													// Métodos	
    	cumplirAnos: function(incremento){
			this.edad = this.edad + incremento;
		}
};

ana.cumplirAnos(1);
console.log(`Nombre: ${agustin.nombre} y edad : ${agustin.edad}`);
```

##**<u style="color:#2980B9">4.- CLASES EN ESMAC 6</u>**
ES6 (entre otras novedades) incorpora una nueva forma de definir clases. Esto hará que los programadores que vienen de otros lenguajes se sientan mas cómodos y que podamos aplicar conceptos de la POO como la herencia.
La sintaxis de clases es muy similar a lenguajes como JAVA o C#:

```javascript
class personaClass {
	constructor(nombre, edad) {
		this._nombre = nombre;
		this._edad = edad;
	}
	
    get edad() {
		return this._edad;
	}
	
    set edad(valor) {
		this._edad = valor;
	}

    cumplirAnos(incremento){
		this.edad = this.edad + incremento;
	}

    imprimirInfo() {
		console.log(`Nombre ${this.nombre}`);
		document.write(`Edad ${this.edad}`;
}

    static confirmacion() {
		console.log("Enhorabuena esta funcionando la clase Persona");
	}
}

	var mama = new personaClass("Ana", 67);
	mama.cumplirAnos(1);
	mama.imprimirInfo();
	mama.edad;
	personaClass.confirmacion();
```

**<span style="color:#2980B9">Constructor</span>**

El constructor es un método especial que inicializa una instancia de la clase. En JavaScript solo puede haber un constructor, no se admite la sobrecarga. Hemos visto en los ejemplos anteriores que usaremos this para asignar los valores contextuales y que podemos usar valores por defecto.

```javascript
constructor(nombre, edad) {
	this._nombre = nombre;
	this._edad = edad;
}
```


###**<span style="color:#2980B9">Getter y Setter</span>**
Estos métodos de acceso nos permiten obtener y asignar valores a los atributos de los objetos. En JavaScript estos métodos se corresponden con atajos sintácticos sin funcionalidad adicional. Deberemos tener en cuenta que podemos caer en una referencia circular lo que daría lugar a un desbordamiento. El uso del guion bajo evitará estos errores.

```javascript
get edad() {
	return this._edad;
}
set edad(valor) {
	this._edad = valor;
}
```



###**<span style="color:#2980B9">Herencia</span>**
Una vez que JS tiene clases, podemos esperar crear clases hijas a partir de otras, o como también se suele expresar: crear clases que extiendan a otras.

```javascript
class nieto extends personaClass {

    constructor(nombre, edad, cuidador) {
		super(nombre, edad);
		this.cuidador = cuidador;
	}

    	imprimirInfo() {
			super.imprimirInfo();
			console.log(` Cuidador ${this.cuidador}`);
		}
    var miguel = new nieto("Miguelito",6 , "Saly");
	miguel.imprimirInfo();
	miguel.cumplirAnos(1);
	console.log(` Edad ${ miguel.edad}`);
```



##**<u style="color:#2980B9">5.- TRABAJANDO CON CLASES</u>**

###**<span style="color:#2980B9">ToString()</span>**
Al convertir un objeto a string (por ejemplo al concatenarlo con un String) se llama al método .toString() del
mismo, que devuelve [object object]. Podemos sobrecargar este método para que devuelva lo que queramos:

```javascript
class personaClass {

	toString() {
		return this.nombre
	}
}

let cpo = new personaClass('Paco', 19);
console.log(`Persona: ${cpo}`)			// imprime 'Persona: Paco'
	
```


###**<span style="color:#2980B9">valueOf()</span>**
Al comparar objetos (con >, <, ...) se usa el valor devuelto por el método .toString() pero si sobrecargamos el método .valueOf() será este el que se usará en comparaciones:

```javascript
class personaClass {
...
	valueOf() {
		return this.edad
	}
}

let cpo = new personaClass('Carlos', 19)
let aat = new personaClass('Ana', 23)
console.log(cpo < aat) // imprime true ya que 19<23

```


###**<span style="color:#2980B9">Prototipos</span>**
Cada objeto tiene un prototipo del que hereda sus propiedades y métodos (es el equivalente a su clase, pero en realidad es un objeto que está instanciado). Si añadimos una propiedad o método al prototipo se añade a todos los objetos creados a partir de él lo que ahorra mucha memoria.

```javascript
personaClass.prototype.getInfo2 = function() {
	return 'Estoy añadiendo una nueva función'
}

let cpo = new personaClass('Carlos', 19)
console.log(cpo.getInfo2())  			// imprime: 'Estoy añadiendo una nueva función'
```

