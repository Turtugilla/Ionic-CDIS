
JavaScript es un lenguaje que va creciendo es muy usado.
* Node permite correr JavaScript del lado del servidor, mostrando grandes sitios webs con sesiones, interacción con bases de datos.
* Apache Cordova: corre aplicaciones nativas de telefono mobiles usando HTML, CSS, y JavaScript.
* Project Kinoma usa JavaScript para manejar dispositivos para Internet de las Cosas.

TypeScript es un lenguaje altamente tipado, lenguaje orientado a objetos que usa un compilador para generar JavaScript.

## Introduciendo JavaScript
Desarrollado oor Anders Hejlsberg de Microsoft (diseñador de C#) y es projecto open source que sirve para ayudar a los desarrolladores a escribir enterprise-scale JavaScript.

Ventajas de TypeScript.
* Compilación
* Fuertemente tipado
* Enpasulación

JavaScript es un lenguaje interpretado y necesita correrse en un interprete para probar que es válido. caso contrario que en TypeScript 
va compilar el código y generar errores de compilación para encontrar por ejemplo errores de sintaxis.

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



sintaxis.
```typescript
declare function describe(
  description: string,
  specDefinitions: () => void
): void;
```

