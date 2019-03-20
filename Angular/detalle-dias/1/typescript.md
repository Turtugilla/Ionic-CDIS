
JavaScript es un lenguaje que va creciendo es muy usado.
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

var myVariable = "test";
console.log(`myVariable=${myVariable}`);

### any
Especifica que un objeto puede tener cualquier tipo.

### const
Si una variable es marcada como const, entonces su valor solo puede ser asignado cuando la variable se define.


### Functions
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

#### Functions callbacks


