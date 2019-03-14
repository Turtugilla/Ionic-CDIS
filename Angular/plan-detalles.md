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
Agregar el css de detalles.
Al final del día debe estar la pantalla con los detalles.

  
  

### Día 2
1. Creando Servicios
```
ng generate service producto
```
Producto.Component vamos a inyectar el Service.Producto
Primero se necesita asignar el Servicio a la dependency injection por medio de un provider. A provider is something 
that can create or deliver a service.
Producto Service -> obtenerProductos(): Observable<Producto[]>


```typescript
 constructor(private productoService: ProductoService) {
   }
```
The parameter simultaneously defines a private heroService property and identifies it as a HeroService injection site.
When Angular creates a HeroesComponent, the Dependency Injection system sets the heroService parameter to the singleton instance of HeroService. 

#### Mensajes.
Generar componente mensajes
```
ng generate component mensajes
```

Generar servicio mensajes
```
ng generate service mensaje
```
MensajeService se deberá inyectar en ProductoService y MensajesComponent. 
ProductoService lo necesita para utilizar el método add y agregar un mensaje. 
MensajesComponent para mostrar el atributo mensajes[] en pantalla. 
Esta DE se logra importando la clase MensajeService en el componente o servicio donde se requiere inyectar y se agrega a
el constructor una instancia de MensajeService:
private mensajeService: MensajeService


### Día 3
#### Routing
La mejor práctica es cargar y configurar el router en un separado, top-level modulo que esta dedicado a el routing y es 
importado por el root AppModule.
Por convención, el modulo class name es AppRoutingModule en src/app folder.
Se va usar el CLI para generarlo.
```
ng generate module app-routing --flat --module=app
```
--flat pone el archivo in src/app en lugar de su propio folder
--module==app dice al CLI que registre los imports  en el array the AppModule.

**Routes** dice al router que vistas debe mostrar cuando un usuario haga click en un link o pegue la  URL en el browser barra
de dirección.
Normalmente un Angular Route tiene dos propiedades:
* path: es un string que es a un URL en el browser barra de dirección
* component: el componente que el router debería crear cuando esta navegando hacia esta ruta.
Se quiere navegar hacia ProductosComponent.
1. Importar ProductosComponent para poderlo referenciar en el Route. Definir un array de Router con un solo route 
para ese componente.
2. app.component.html -> router-outlet le dice a el router donde mostrar las vistas routed.
El RouterOutlet es una de las directivas de routes que se hacen disponibles para el AppComponent por que  AppModule
 importa AppRoutingModule que a la vez exporta RouterModule.
#### Agregar un DashBoard.
1. Generar el componente DashBoard.
2. Hay que agregar el CSS, HTML  y TS
3. Agregarlo en el RoutingModule
4. Agregar los links en component root html.

#### Detalles de los Productos  Route.
1. Se agrega Componente DP a el AppModule Routing
2. Con el path detail/:id
Agregar el goback button


### Día 4
#### Trabajando con imagenes



### Día 5 
HTTP Client.
Que es lo que se hará aqui
1. ProductoService va obtener los productos con HTTP requests
2. Agregar, Editar y Eliminar productos y guardar estos cambios con HTTP.
3. Busqueda de productos por nombre
Habilitar HTTP Services
1. Agregandolo en el root module. y en el imports array
Vamos a simular comunicación con un server remoto usando in memory Web API.
2. Se agrega la data que estaba en mock-productos en in-memory-data.service
Productos y HTTP

### Día 6 Angular Primefaces




