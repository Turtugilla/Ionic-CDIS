## Día 1
#### ¿Qué es Angular?
1. Framework  y Plataforma client-side
2. Es una herramienta que te va ayudar a construir aplicaciones modernas para la web, mobile o escritorio.
3. Angular esta escrito en TypeScript, que es un superset of JavaScript
4. TypeScript
  * Lenguaje Tipado.
  * 

#### Configurando el Entorno de Desarrollo
1. Hay que instalar Node.js y NPM
2. Instalar Angular CLI:```npm install -g @angular/cli ```
3. Visual Studio Code

#### Creando la aplicación
1. Correr el siguien comando CLI :           ```ng new catalogo-productos ``` -> Creando la aplicación
2. Recorrer el código que se genero. Mostrar la unión de los datos entre componentes.
```html
app.component.html
<div style="text-align:center">
  <h1>
    {{ title }}
  </h1>
</div>
```
```typescript
app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Catalogo Productos';
}
```

3. Generar un componente ```ng generate component productos```. Para esto ya se puede agreger el css en componente root.
  * Las aplicaciones estan construidas usando componentes
  * Un conjunto de funcionalidades  que incluyen una vista, stilos y controlador.
  * Mostrar como utilizar el selector en la app.component root.
4. Separar en una clase un producto con los siguientes atributos: id, nombre, marca, cantidad, imagen
5. El siguiente código primero se va poner en el componente productos.ts para mostrar los datos. Despues se va pasar
a un nuevo componente. Se debe importar FormsModule en el modulo root. 
```html
<div *ngIf="producto">
  <h2>{{producto.nombre | uppercase}} Detalles</h2>

  <div>
    <label>id:
      <input [(ngModel)]="producto.id" placeholder="id">
    </label>
  </div>
```
6. Crear datos en nueva clase mock-productos.ts y mostrar los datos en un productos.component.ts. 
Al final de esta parte se añade el css
```html
<h2>Mis Productos</h2>
 <ul class="productos">
   <li *ngFor="let producto of productos" 
       (click)="onSelect(producto)"
       [class.selected]="producto === productoSeleccionado">
     <span class="badge">{{producto.id}}</span> {{producto.nombre}}
   </li>
</ul>
```
```typescript
import { Component, OnInit } from '@angular/core';
import {Producto} from '../producto';
import {PRODUCTOS} from '../mock-productos';


@Component({
  selector: 'app-productos',
  templateUrl: './productos.component.html',
  styleUrls: ['./productos.component.css']
})
export class ProductosComponent implements OnInit {


  constructor() { }

  ngOnInit() {

  }
  productos = PRODUCTOS;
  productoSeleccionado: Producto;
  onSelect(producto: Producto): void{
    this.productoSeleccionado = producto;
  }

}
```

7. Generar detalles-producto.component para separar los detalles de el producto.
Solamente se agrega el 
```typescript 
@Input() producto: Producto 
``` 
y en el html de productos.componente 
```html 
<app-detalles-producto [producto]="productoSeleccionado"></app-detalles-producto> 
```



  
  

### Día 2

