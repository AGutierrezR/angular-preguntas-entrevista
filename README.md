# Angular Preguntas y Respuestas

### Tabla de Contenido

| No. | Preguntas                                                                                            |
| --- | ---------------------------------------------------------------------------------------------------- |
| 1   | [Que es Angular?](#que-es-angular)                                                                   |
| 2   | [Cual es la diferencia entre AngujarJS y Angular?](#cual-es-la-diferencia-entre-angujarjs-y-angular) |
| 3   | [Que es TypeScript?](#que-es-typescript) |
| 4   | [Cuales son los componentes claves de Angular?](#cuales-son-los-componentes-claves-de-angular) |
| 5   | [Que es un Directive?](#que-es-un-directive) |
| 6   | [Que es un Component?](#que-es-un-Component) |
| 7   | [Cual es la diferencia entre Components y Directives?](#cual-es-la-diferencia-entre-components-y-directives) |

1. ### Que es Angular?

   Angular es una plataforma front-end basada en TypeScript que facilita la creación de aplicaciones web/mobile/desktop. Las características principales de este marco, como las plantillas declarativas, la inyección de dependencias, las herramientas de extremo a extremo y muchas otras características, se utilizan para facilitar el desarrollo.

   **[⬆ Ir Arriba](#tabla-de-contenido)**

2. ### Cual es la diferencia entre AngujarJS y Angular?

   Angular esta basado completamente en componentes en donde una aplicación es un árbol de componentes individuales

   Algunas de las mayores diferencias son:

   | AngularJS                                                 | Angular                                        |
   | --------------------------------------------------------- | ---------------------------------------------- |
   | Esta basado en la arquitectura MVC                        | Esta basadi eb Service/Controller              |
   | Usa JavaScript para construir la aplicacion               | Usa TypeScript para construir la aplicacion    |
   | Basado en el concepto de controladores                    | Tiene un enfoque de UI basado en componentes   |
   | No es un framework compatible con dispositivos mobile     | Desarrollado considerando la plataforma mobile |
   | Dificultades para crear una aplicacion compatible con SEO | Es facil crear una aplicion compatibe con SEO  |

   **[⬆ Ir Arriba](#tabla-de-contenido)**

3. ### Que es TypeScript?

   TypeScript es un subconjunto de JavaScript creado por Microsoft que agregar optional types, classes, async/await, y muchas otras características, y compila JavaScript plano. Angular esta construido completamente en TypeScript y se usa como lenguaje primario. Se puede instalar globalmente

   ```shell
   npm install -g typescript
   ```

   Un simple ejemplo de como se usa TypeScript

   ```ts
   function greeter(person: string) {
   	return "Hello, " + person;
   }

   let user = "Sudheer";
   document.body.innerHTML = greeter(user);
   ```

   El metodo `greeter` solo permite un argumento de tipo string

   **[⬆ Ir Arriba](#tabla-de-contenido)**

4. ### Cuales son los componentes claves de Angular?

   1. Component: Son los bloque de construcción basicos de una aplication angular para controlar las vistas HTML.
   2. Modules: En angular un modulo es un conjunto de bloques de construcción basicos como components, directives, services, etc. Una aplicación esta dividida en piezas lógicas y cada pieza de código se denomina "module" que realiza una tarea
   3. Template: Representa una vista en una aplicación Angular
   4. Services: Se usa para crear componentes que pueden ser compartidos a través de toda la aplicación
   5. Metadata: Pueden ser usadas para agregar mas datos a una clase de Angular

   **[⬆ Ir Arriba](#tabla-de-contenido)**

5. ### Que es un Directive?

   Los directive añaden comportamiento un elementos existentes en el DOM o a una instancia de componente existente

   ```ts
   import { Directive, ElementRef, Input } from '@angular/core';

   @Directive({ selector: '[myHighlight]' })
   export class HighlightDirective {
   	constructor(el: ElementRef) {
   		el.nativeElement.style.backgroundColor = 'yellow';
     }
   }
   ```

   Esta directive extiende el comportamiento del elemento HTML con un fondo amarillo

   ```html
   <p myHighlight>Highlight me!</p>
   ```

   **[⬆ Ir Arriba](#tabla-de-contenido)**

6. ### Que es un Component?

   Los Components son los bloques de construcción de UI mas básicos en una aplicación Angular que formaba un árbol de componentes Angular. Estos componentes son un subconjunto de los directives. A diferencia de los directive, los componentes siempre tendrán una plantilla y solo se puede crear una instancia de un componente por elemento en un template. Aquí un simple ejemplo de un componente de Angular:

   ```ts
   import { Component } from '@angular/core';

   @Component ({
   	selector: 'my-app',
   	template: ` <div>
   		<h1>{{title}}</h1>
   		<div>Learn Angular6 with examples</div>
   	</div> `,
   })

   export class AppComponent {
   	title: string = 'Welcome to Angular world';
   }
   ```

   **[⬆ Ir Arriba](#tabla-de-contenido)**

7. ### Cual es la diferencia entre Components y Directives?

   En resumen un componente (`@component`) es un directive con un template.

   Alguna de las diferencias mas sustanciales son:

   | Component                                                    | Directive                                                    |
   | ------------------------------------------------------------ | ------------------------------------------------------------ |
   | Para registrar un component se usa el meta-data  `@Component` | Para registrar un directive se usa el meta-data `@Directive` |
   | Los components normalmente se usan para crear algun Widget en el UI | Los Directive se usan para agregar comportamiento a elementos existentes en el DOM |
   | Los Components  se usan para separar una aplicacion en pequeños componentes | Los Directive se usan para diseñar componentes reusables     |
   | Solo puede haber un componente por elemento DOM              | Se pueden usar muchas directivas por elemento DOM            |
   | El decorator @View o templateurl / template son obligatorios | Los Directive no usan View                                   |

   **[⬆ Ir Arriba](#tabla-de-contenido)**

8. ### Que es un Template?

   Un templatees una vista HTML donde se muestran los datos uniendo controles a propiedades de un componente Angular. Se pueden guardar las los templatede los componentes en uno de dos lugares. Puedes declararlos en lineausando la propiedad template, o puede definirlo en un fichero HTML separado y vincularlo en el metadatade componente usando el decorador `@Component` con la propiedad `templateUrl`

   Usando inline template:

   ```ts
   import { Component } from '@angular/core';

   @Component ({
      selector: 'my-app',
      template: `
         <div>
            <h1>{{title}}</h1>
            <div>Learn Angular</div>
         </div>
      `
   })

   export class AppComponent {
      title: string = 'Hello World';
   }
   ```

   Usando un fichero separado:

   ```ts
   import { Component } from '@angular/core';

   @Component ({
      selector: 'my-app',
      templateUrl: 'app/app.component.html'
   })

   export class AppComponent {
      title: string = 'Hello World';
   }
   ```
