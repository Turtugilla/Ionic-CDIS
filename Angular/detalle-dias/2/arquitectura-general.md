Angular es una plataforma y framework para construir aplicaciones enfocadas en el cliente
en HTML y TypeScript.
Está escrito en TypeScript


> [Plataforma: Sirve de apoyo o base para algo

> Framework: una estructura conceptual y tecnológica de asistencia definida, normalmente, con artefactos o módulos concretos de software, 
 que puede servir de base para la organización y desarrollo de software ]

Bloques Básicos de Construccion de aplicaciones Angular son los NgModule -> Proveen 
un contexto de compilación para componentes.

¿Qué Hacen los módulos?
Recolectan código que este relacionado en conjuntos funcionales.
Una Aplicación Angular esta definida por un set de NgModules.
Una aplicación debe tener al menos un root module que habilita el bootstrapping.

**Componentes** definen vistas. Son un conjunto de elementos de pantalla que angular 
escoge y modifica de acuerdo a la lógica y datos del programa.

Componentes usan **SERVICIOS**, que proveen funcionalidad especifica no directamente relacionada
a las vistas. Los Servicios pueden ser inyectados en los componentes como dependencias.

Ambos tanto los Componentes y Servicios son simples clases con **DECORADORES** que marcan su
tipo y proveen metada que dice a Angular como usarlas.

### Componentes

Un template combina html con sintaxis angular que puede modificar elementos antes de que
sean mostrados.

Template Directives: proveen lógica del programa

Binding MarkUp: conecta los datos de tu aplicacion y el DOM.
Hay dos tipos de data binding:

Event Binding: permite a la aplicación responder a entradas de usuario al actualizar los 
datos.

Property Binding: Intepolar valores que son procesados por la aplicacion hacia el HTML. 




