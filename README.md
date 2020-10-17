# Angular Preguntas y Respuestas

### Tabla de Contenido

| No. | Preguntas                                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------ |
| 1   | [Que es Angular?](#que-es-angular)                                                                           |
| 2   | [Cual es la diferencia entre AngujarJS y Angular?](#cual-es-la-diferencia-entre-angujarjs-y-angular)         |
| 3   | [Que es TypeScript?](#que-es-typescript)                                                                     |
| 4   | [Cuales son los componentes claves de Angular?](#cuales-son-los-componentes-claves-de-angular)               |
| 5   | [Que es un Directive?](#que-es-un-directive)                                                                 |
| 6   | [Que es un Component?](#que-es-un-Component)                                                                 |
| 7   | [Cual es la diferencia entre Components y Directives?](#cual-es-la-diferencia-entre-components-y-directives) |
| 8   | [Que es un Template?](#que-es-un-template)                                                                   |
| 9   | [Que es un Module?](#que-es-un-module)                                                                       |
| 10  | [Cuales son los lifecycle hooks disponbles?](#cuales-son-los-lifecycle-hooks-disponbles)                     |
| 11  | [Que es enlace de datos (data binding)?](#que-es-enlace-de-datos-(data-binding))                             |

1. ### Que es Angular?

   Angular es una plataforma front-end basada en TypeScript que facilita la creación de aplicaciónes web/mobile/desktop. Las características principales de este marco, como las plantillas declarativas, la inyección de dependencias, las herramientas de extremo a extremo y muchas otras características, se utilizan para facilitar el desarrollo.

   **[⬆ Ir Arriba](#tabla-de-contenido)**

2. ### Cual es la diferencia entre AngujarJS y Angular?

   Angular esta basado completamente en componentes en donde una aplicación es un árbol de componentes individuales

   Algunas de las mayores diferencias son:

   | AngularJS                                                 | Angular                                        |
   | --------------------------------------------------------- | ---------------------------------------------- |
   | Esta basado en la arquitectura MVC                        | Esta basadi eb Service/Controller              |
   | Usa JavaScript para construir la aplicación               | Usa TypeScript para construir la aplicación    |
   | Basado en el concepto de controladores                    | Tiene un enfoque de UI basado en componentes   |
   | No es un framework compatible con dispositivos mobile     | Desarrollado considerando la plataforma mobile |
   | Dificultades para crear una aplicación compatible con SEO | Es facil crear una aplicion compatibe con SEO  |

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

   El método `greeter` solo permite un argumento de tipo string

   **[⬆ Ir Arriba](#tabla-de-contenido)**

4. ### Cuales son los componentes claves de Angular?

   1. Component: Son los bloque de construcción basicos de una aplication angular para controlar las vistas HTML.
   2. Modules: En angular un módulo es un conjunto de bloques de construcción basicos como components, directives, services, etc. Una aplicación esta dividida en piezas lógicas y cada pieza de código se denomina "module" que realiza una tarea
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

   | Component                                                                   | Directive                                                                          |
   | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
   | Para registrar un component se usa el meta-data  `@Component`               | Para registrar un directive se usa el meta-data `@Directive`                       |
   | Los components normalmente se usan para crear algun Widget en el UI         | Los Directive se usan para agregar comportamiento a elementos existentes en el DOM |
   | Los Components  se usan para separar una aplicación en pequeños componentes | Los Directive se usan para diseñar componentes reusables                           |
   | Solo puede haber un componente por elemento DOM                             | Se pueden usar muchas directivas por elemento DOM                                  |
   | El decorator @View o templateurl / template son obligatorios                | Los Directive no usan View                                                         |

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

   **[⬆ Ir Arriba](#tabla-de-contenido)**

9. ### Que es un Module?

   Los módulos son las fronteras lógicas de la aplicación, y la aplicación esta dividida en módulos separados para separar la funcionalidad de la aplicación. Vamos a ver un ejemplo de la raíz **app.module.ts**

   ```ts
   import { NgModule }      from '@angular/core';
   import { BrowserModule } from '@angular/platform-browser';
   import { AppComponent }  from './app.component';

   @NgModule ({
      imports:      [ BrowserModule ],
      declarations: [ AppComponent ],
      bootstrap:    [ AppComponent ],
      providers: []
   })
   export class AppModule { }
   ```

   El decorator `NgModule` tiene 5 opciones importantes (aparte de todo)

   1. La opction `imports` es usado para importar otras módulos dependientes. El `BrowserModulee` es requerido por defecto en cualquier aplicación basada en web.
   2. La opción `declarations` es para definir los componentes en el módulo respectivo
   3. La opción `bootstrap` le dice a Angular, cuales son los componentes para arrancar la aplicación
   4. La opcon `providers` configura el conjunto de injectable objects que estaran disponibles en el injecto para este módulo
   5. La opción `entryComponents` es el conjunto de componentes que de cargaran dinamicamente en el view

   **[⬆ Ir Arriba](#tabla-de-contenido)**

10. ### Cuales son los lifecycle hooks disponbles?

    Las aplicaciónes de Angular van por un conjunto de procesos o tiene ciclos de vida desde inicialización hasta el final de la aplicación.

    Los ciclos de angular son:

    1. **ngOnChanges**: Cuando un valor de una propiedad enlazada a datos cambia, se llama a este método.
    2. **ngOnInit**: Es llamado siempre que ocurra la inicialización de un directive/component despues de que Angular muestra por primera vez las propiedades vinculada a los datos.
    3. **ngDoCheck**: Este es para la detección y para actuar sobre los cambios que Angular no puede o no detecta por si solo.
    4. **ngAfterContentInit**: Es llamado después de que Angular ha inicializado todo el contenido de un directive. Se define para manejar cualquiera tarea de inicialización adicional.
    5. **ngAfterContentChecked**: Se llama después de que la detección de cambios predeterminada haya completado la comprobación de todo el contenido de un directive.
    6. **ngAfterViewInit**: Se llama después de que Angular haya inicializado completamente la vista de un componente y las vistas secundarias. Se define para manejar cualquiera tarea de inicialización adicional
    7. **ngAfterViewChecked**: Se llama después de que la detección de cambios predeterminada haya completado la comprobación de cambios en la vista de un componente.
    8. **ngOnDestroy**: Esta es la fase de limpieza justo antes de que Angular destruya el directive/component.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

11. ### Que es enlace de datos (data binding)?
    
    Data bindinges un concepto fundamental en Angular y permite definir comunicación entre un componente y el DOM, haciendo fácil definir aplicaciónes interactivas sin preocupaciones sobre enviar y recuperar datos. Existen cuatro formas de data binding(dividido en 3 categorías):
    
    1. **Desde el Component a el DOM (Mostrando datos)** 

       **Interpolation**: {{ value }}: Añade el valor de una propiedad desde el componente

       ```html
       <li>Name: {{ user.name }}</li>
       <li>Address: {{ user.address }}</li>
       ```

       **Property binding**: [property]="value": El valor es pasado desde el componente hacia un propiedad especifica o un atributo de HTML

       ```html
       <input type="email" [value]="user.email">
       ```

    2. **Desde el DOM hacia el componente (Reaccionando a eventos)**

       **Event binding**: (event)="function": Cuando un evento especifico del DOM ocurre (ej.: click, change, keyup), se llama a el método especificado en el componente

       ```html
       <button (click)="logout()"></button>
       ```

    3. **Two-way binding (Combinacion de ambas)**

       **Two-way data binding**: [(ngModel)]="value": Te permite tener un flujo de datos en dos sentidos. Por ejemplo, en el siguiente código, ambos el email input del DOM y la propiedad email del componente están sincronizados

       ```html
       <input type="email" [(ngModel)]="user.email">
       ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

12. ### Que son los metadatos (metadata)?

    Son usados para decorar clases de modo que pueda configurar el comportamiento esperado de la clase. Los meta datos están representados por decoradores.

    1. **Decoradores de clases**: (@Component y @NgModule)

       ```ts
       import { NgModule, Component } from '@angular/core';

       @Component({
       	selector: 'my-component',
       	template: '<div>Class decorator</div>',
       })
       export class MyComponent {
       	constructor() {
       		console.log('Hey I am a component!');
       	}
       }

       @NgModule({
       	imports: [],
       	declarations: [],
       })
       export class MyModule {
       	constructor() {
       		console.log('Hey I am a module!');
       	}
       }
       ```

    2. **Decoradores de propiedades**: Usado para propiedades dentro de las clases (ej.: @Input y @Output)

       ```ts
       import { Component, Input } from '@angular/core';

       @Component({
       	selector: 'my-component',
       	template: '<div>Property decorator</div>'
       })

       export class MyComponent {
       	@Input()
       	title: string;
       }
       ```

    3. **Decoradores de métodos**: Usado para métodos dentro de la clase (ej.: @HostListener)

       ```ts
       import { Component, HostListener } from '@angular/core';

       @Component({
       	selector: 'my-component',
         template: '<div>Method decorator</div>'
       })
       export class MyComponent {
       	@HostListener('click', ['$event'])
         onHostClick(event: Event) {
           // clicked, `event` available
         }
       }
       ```

    4. **Decoradores de parámetros**: Usado para parámetros dentro del constructor de una clase (ej.: @Inject, Optional)

       ```ts
       import { Component, Inject } from '@angular/core';
       import { MyService } from './my-service';

       @Component({
       	selector: 'my-component',
       	template: '<div>Parameter decorator</div>'
       })
       export class MyComponent {
       	constructor(@Inject(MyService) myService) {
       		console.log(myService); // MyService
       	}
       }
       ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

13. ### Que es un service?

    Un services es usado cuando se necesita proporcionar una funcionalidad común a varios módulos. Los servicios permiten una mayor separacion de preocupación para la aplicación y una mejor modularidad al permitir extraer funcionalidades en comun de los componentes.

    Creemos un repoService que puede ser usado en varios componentes

    ```ts
    import { Injectable } from '@angular/core';
    import { Http } from '@angular/http';

    @Injectable({ // The Injectable decorator is required for dependency injection to work
      // providedIn option registers the service with a specific NgModule
      providedIn: 'root',  // This declares the service with the root app (AppModule)
    })
    export class RepoService{
      constructor(private http: Http){
      }

      fetchAll(){
        return this.http.get('https://api.github.com/repositories');
      }
    }
    ```

    El servicio anterior utiliza el servicio `Http` como dependencia.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

14. ### Cual es la diferencia entre el constructor y ngOnInit?

    Las clases de TypeScript tiene por defecto un método llamado `constructor` el cual es usado para propósitos de inicialización. A diferencia de `ngOnInit` que es un método especifico de Angular, usado específicamente para definir Angular Bindings. Aunque el `constructor` es el primero en ser llamado, es preferible dejar los Angular binding en el método `ngOnInit`. Para usar `ngOnInit` debemos implementar `OnInit`.

    ```ts
    export class App implements OnInit{
    	constructor(){
    		//called first time before the ngOnInit()
      }
    
      ngOnInit(){
    		//called after the constructor and called  after the first ngOnChanges()
      }
    }
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

15. ### Que es Dependency Injection en Angular?

    Dependency Injection (DI), es un muy importante patrón de diseño de aplicaciónes en el que una clase pide dependencias de una fuente externas en vez de crear por si misma. Angular viene como su propio framework DI, para solucionar dependencias (servicios u objetos que una clase necesita para realizar su función). Se puede tener servicios que dependen de otros servicios atrevés de toda la aplicación.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

16. ### Cuales son los tipos de Directives que existen?

    Existen tres tipos de Directives

    1. **Components**: Directive con templates
    2. **Structural directive**: Cambian la diagramación del DOM agregando un quitando elementos del DOM
    3. **Attribute directives**: Cambian la apariencia o comportamiento de un componente, elemento, u otro directive.

    En la siguiente tabla hay una diferencia entre Structural directive y Attribute directives

    | Structural Directives                                        | Attribute Directives                                         |
    | ------------------------------------------------------------ | ------------------------------------------------------------ |
    | Luce como un atributo HTML normal pero con un `*` adelante   | Lucen como un atributo HTML normal (posiblemente con un databinding o event binding) |
    | Afecta un area completa del DOM (elementos son agregados o quitados) | Solo afectan/cambian el elemento en donde son agregados      |

    **[⬆ Ir Arriba](#tabla-de-contenido)**

17. ### Cual es el propósito de async pipe?

    El AsyncPipe se suscribe a un observable o promesa y retorna el ultimo valor ha emitido. Cuando un nuevo valor es emitido, el pipe marca el componente para detectar cambios.

    Tomemos como ejemplo un time observable que se actualiza constantemente (cada dos segundos)

    ```ts
    @Component({
      selector: 'async-observable-pipe',
      template: `<div><code>observable|async</code>:
           Time: {{ time | async }}</div>`
    })
    export class AsyncObservablePipeComponent {
      time = new Observable(observer =>
        setInterval(() => observer.next(new Date().toString()), 2000)
      );
    }
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

18. ### Cual es el propósito del directive ngFor?

    En Angular se usa ngFor en un template para mostrar cada item de una lista. Por ejemplo, si se quiere iterar en la lista de usuarios

    ```html
    <li *ngFor="let user of users">
      {{ user }}
    </li>
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

