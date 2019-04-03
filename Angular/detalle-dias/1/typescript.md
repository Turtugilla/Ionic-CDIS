
## Cap 2 Tipos, Variables y Técnicas de Funciónes
JavaScript es un lenguaje que va creciendo es muy usado. (Presentar gráficas)
* Node permite correr JavaScript del lado del servidor, mostrando grandes sitios webs con sesiones, interacción con bases de datos.
* Apache Cordova: corre aplicaciones nativas de telefono mobiles usando HTML, CSS, y JavaScript.
* Project Kinoma usa JavaScript para manejar dispositivos para Internet de las Cosas.
___

TypeScript es un lenguaje altamente tipado, lenguaje orientado a objetos que usa un compilador para generar JavaScript.
(Imagen mostrando que es TypeScript)
___
## Introduciendo JavaScript
Desarrollado oor Anders Hejlsberg de Microsoft (diseñador de C#) y es projecto open source que sirve para ayudar a los desarrolladores a escribir enterprise-scale JavaScript.

Ventajas de TypeScript.
* Compilación
* Fuertemente tipado
* Enpasulación

JavaScript es un lenguaje interpretado y necesita correrse en un interprete para probar que es válido. caso contrario que en TypeScript 
va compilar el código y generar errores de compilación para encontrar por ejemplo errores de sintaxis.
___

### Altamente tipado.
```javascript
// JavaScript
var test = "this is a string";
test = 1;
test = function(a,b){
  return a + b;
}
```

```typescript
//TypeScript
var test: string = "this is a string";
test = 1;
test = function(a,b){ return a + b }
```

___

Analizando Sintaxis.
```typescript
declare function describe(
  description: string,
  specDefinitions: () => void
): void;
```
Typescript utiliza los doble paréntesis `()` sintaxis para declarar funciones y la flecha `=>` para mostrar el tipo de retorno
de la función

___

Definition de Clase
```typescript
class MyClass{
  add(x,y){
    return x + y
  }
}
```

### Public and Private 
Pendiente



### IDE
Visual Studio Code
#### Debugging
Create a launch.json file.

### Template Strings
TypeScript permite utilizar la sintaxis template string ES6. Esta sintaxis provee un metodo conveniente for inyectar valores a string.

```typescript
var myVariable = "test";
console.log(`myVariable=${myVariable}`);
```
### any
Especifica que un objeto puede tener cualquier tipo.

### const
Si una variable es marcada como const, entonces su valor solo puede ser asignado cuando la variable se define.


### Functions

Comparar estas dos funciones 
```typescript
function addNumbers(a: number, b: number) : string{
  return (a + b).toString();
}

var addResult = addNumbers(2,3);
console.log(`addNumbers returned: ${addResult}`);
```

```typescript
function addNumbers(a: number, b: number) : string{
  return a + b;
}

var addResult = addNumbers(2,3);
console.log(`addNumbers returned: ${addResult}`);
```
___
#### Funciones anónimas
Funciones que estan definidas en el aire y no especifican un nombre de función.
```typescript
var addFunction =  function(a: number, b:number) : number{
  return a + b;
 }
 
 var addFunctionResult = addFunction(2,3);
 console.log(`addFunctionResult: ${addFunctionResult}`);

```

#### Functions callbacks
Una de las mas poderosas características de JavaScript y tambien es la tecnología en que Node ha sido construido es el concepto de 
**callback functions**
Una callback function es una función que se pasa en otra funcion y generalmente es invocada dentro de la función.

```typescript
//Ejemplo en JavaScript
var callbackFunction = function(text){
  console.log('inside callbackFunction ' + text);
}

function doSomethingWithCallback(initialText, callback){
  console.log('inside doSomethingWithCallback ' + initialText);
  callback(initialText);
}

doSomethingWithACallback('myText', callbackFunction);

```

```typescript
//Ejemplo en typescript

function callbackFunction(text: string){
  console.log(`inside callbackFunction ${text}`);
}

function doSomethingWithACallback(
    initialText: string,
    callback : (initialText: string) => void
 ) {
  console.log(`inside doSomethingWithCallback ${initialText}`);
  callback(initialText);
 }
 
 doSomethingWithCallback("myText", callbackFunction);
```

Cap 3 Interfaces, Clases y Herencia

### Interfaces.
Proveen un mecanismo para definir que propiedades y métodos un objeto debe implementar. 
Es una manera de definir un tipo custom.

```typescript
interfaces IComplexType {
  id: number;
  name: string;
}

```
Esta definición de interface puede ser aplicada para una variable:

```typescript
  let complexType : IComplexType;
  complextType = {id: 1, name: "test"};
```

Las interfaces son un compile-time caracteristica del lenguaje TypeScript y el compilador no genera ningun código
JavaScript de las interfaces.

### Clases
Una clase es una definición de un objeto



