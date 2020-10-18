# Angular Preguntas y Respuestas

### Tabla de Contenido

| No.  | Preguntas                                                    |
| ---- | ------------------------------------------------------------ |
| 1    | [¿Que es Angular?](#que-es-angular)                          |
| 2    | [¿Cual es la diferencia entre AngujarJS y Angular?](#cual-es-la-diferencia-entre-angujarjs-y-angular) |
| 3    | [¿Que es TypeScript?](#que-es-typescript)                    |
| 4    | [¿Cuales son los componentes claves de Angular?](#cuales-son-los-componentes-claves-de-angular) |
| 5    | [¿Que es un Directive?](#que-es-un-directive)                |
| 6    | [¿Que es un Component?](#que-es-un-Component)                |
| 7    | [¿Cual es la diferencia entre Components y Directives?](#cual-es-la-diferencia-entre-components-y-directives) |
| 8    | [¿Que es un Template?](#que-es-un-template)                  |
| 9    | [¿Que es un Module?](#que-es-un-module)                      |
| 10   | [¿Cuales son los lifecycle hooks disponibles?](#cuales-son-los-lifecycle-hooks-disponibles) |
| 11   | [¿Que es enlace de datos o data binding?](#que-es-enlace-de-datos-o-data-binding) |                                              |
| 12   | [¿Que son los metadatos o metadata?](#que-son-los-metadatos-o-metadata) |
| 13   | [¿Que es un service?](#que-es-un-service)                   |
| 14   | [¿Cual es la diferencia entre el constructor y ngOnInit?](#cual-es-la-diferencia-entre-el-constructor-y-ngOnInit) |
| 15   | [¿Que es Dependency Injection en Angular?](#que-es-Dependency-Injection-en-Angular) |
| 16   | [¿Cuales son los tipos de Directives que existen?](#cuales-son-los-tipos-de-Directives-que-existen) |
| 17   | [¿Cual es el propósito de async pipe?](#cual-es-el-propósito-de-async-pipe) |
| 18   | [¿Cual es el propósito del directive ngFor?](#cual-es-el-propósito-del-directive-ngFor) |
| 19   | [¿Cual es el propósito del directive ngIf?](#cual-es-el-propósito-del-directive-ngIf) |
| 20   | [¿Que es interpolación?](#que-es-interpolación)             |
| 21   | [¿Que son template expressions?](#que-son-template-expressions) |
| 22   | [¿Que son template statements?](#que-son-template-statements) |
| 23   | [¿Como se categorizan los tipos de data binding?](#como-se-categorizan-los-tipos-de-data-binding) |
| 24   | [¿Que son los Pipes?](#que-son-los-Pipes)                   |
| 25   | [¿Que son Pipes Parametrizados?](#que-son-Pipes-Parametrizados) |
| 26   | [¿Como se encadenan los pipes?](#como-se-encadenan-los-pipes) |
| 27   | [¿Que es un custom pipe?](#que-es-un-custom-pipe)           |
| 28   | [Ejemplo de custom pipe](#ejemplo-de-custom-pipe)            |
| 29   | [¿Que es HttpClient y sus beneficios?](#Que-es-HttpClient-y-sus-beneficios) |
| 30   | [¿Como se usa HttpClient con un ejemplo?](#Como-se-usa-HttpClient-con-un-ejemplo) |
| 31   | [¿Como se puede leer el full response?](#Como-se-puede-leer-el-full-response) |
| 32   | [¿Que son los Http Interceptors?](#que-son-los-http-interceptors) |
| 33   | [¿Cuales son las aplicaciónes para los HTTP Interceptos?](#Cuales-son-las-aplicaciónes-para-los-HTTP-Interceptos) |
| 34   | [¿Angular puede soportar varios interceptors?](#Angular-puede-soportar-varios-interceptors) |
| 35   | [¿Como se puede usar interceptor para toda la aplicación?](#Como-se-puede-usar-interceptor-para-toda-la-aplicación) |

1. ### ¿Que es Angular?

   Angular es una plataforma front-end basada en TypeScript que facilita la creación de aplicaciónes web/mobile/desktop. Las características principales de este marco, como las plantillas declarativas, la inyección de dependencias, las herramientas de extremo a extremo y muchas otras características, se utilizan para facilitar el desarrollo.

   **[⬆ Ir Arriba](#tabla-de-contenido)**

2. ### ¿Cual es la diferencia entre AngujarJS y Angular?

   Angular esta basado completamente en componentes en donde una aplicación es un árbol de componentes individuales

   Algunas de las mayores diferencias son:

   | AngularJS                                                 | Angular                                        |
   | --------------------------------------------------------- | ---------------------------------------------- |
   | Esta basado en la arquitectura MVC                        | Esta basado eb Service/Controller              |
   | Usa JavaScript para construir la aplicación               | Usa TypeScript para construir la aplicación    |
   | Basado en el concepto de controladores                    | Tiene un enfoque de UI basado en componentes   |
   | No es un framework compatible con dispositivos mobile     | Desarrollado considerando la plataforma mobile |
   | Dificultades para crear una aplicación compatible con SEO | Es fácil crear una aplicación compatible con SEO  |

   **[⬆ Ir Arriba](#tabla-de-contenido)**

3. ### ¿Que es TypeScript?

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

4. ### ¿Cuales son los componentes claves de Angular?

   1. Component: Son los bloque de construcción básicos de una aplicación angular para controlar las vistas HTML.
   2. Modules: En angular un módulo es un conjunto de bloques de construcción básicos como components, directives, services, etc. Una aplicación esta dividida en piezas lógicas y cada pieza de código se denomina "module" que realiza una tarea
   3. Template: Representa una vista en una aplicación Angular
   4. Services: Se usa para crear componentes que pueden ser compartidos a través de toda la aplicación
   5. Metadata: Pueden ser usadas para agregar mas datos a una clase de Angular

   **[⬆ Ir Arriba](#tabla-de-contenido)**

5. ### ¿Que es un Directive?

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

6. ### ¿Que es un Component?

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

7. ### ¿Cual es la diferencia entre Components y Directives?

   En resumen un componente (`@component`) es un directive con un template.

   Alguna de las diferencias mas sustanciales son:

   | Component                                                                   | Directive                                                                          |
   | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
   | Para registrar un component se usa el meta-data  `@Component`               | Para registrar un directive se usa el meta-data `@Directive`                       |
   | Los components normalmente se usan para crear algún Widget en el UI         | Los Directive se usan para agregar comportamiento a elementos existentes en el DOM |
   | Los Components  se usan para separar una aplicación en pequeños componentes | Los Directive se usan para diseñar componentes reusables                           |
   | Solo puede haber un componente por elemento DOM                             | Se pueden usar muchas directivas por elemento DOM                                  |
   | El decorator @View o templateurl / template son obligatorios                | Los Directive no usan View                                                         |

   **[⬆ Ir Arriba](#tabla-de-contenido)**

8. ### ¿Que es un Template?

   Un template es una vista HTML donde se muestran los datos uniendo controles a propiedades de un componente Angular. Se pueden guardar las los template de los componentes en uno de dos lugares. Puedes declararlos en linea usando la propiedad template, o puede definirlo en un fichero HTML separado y vincularlo en el metadatade componente usando el decorador `@Component` con la propiedad `templateUrl`

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

9. ### ¿Que es un Module?

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

   1. La opción `imports` es usado para importar otras módulos dependientes. El `BrowserModulee` es requerido por defecto en cualquier aplicación basada en web.
   2. La opción `declarations` es para definir los componentes en el módulo respectivo
   3. La opción `bootstrap` le dice a Angular, cuales son los componentes para arrancar la aplicación
   4. La opción `providers` configura el conjunto de injectable objects que estarán disponibles en el injector para este módulo
   5. La opción `entryComponents` es el conjunto de componentes que de cargaran dinámicamente en el view

   **[⬆ Ir Arriba](#tabla-de-contenido)**

10. ### ¿Cuales son los lifecycle hooks disponibles?

    Las aplicaciónes de Angular van por un conjunto de procesos o tiene ciclos de vida desde inicialización hasta el final de la aplicación.

    Los ciclos de angular son:

    1. **ngOnChanges**: Cuando un valor de una propiedad de entrada (input) vinculada cambia, se llama a este método.
    2. **ngOnInit**: Es llamado siempre que ocurra la inicialización de un directive/component después de que Angular muestra por primera vez las propiedades vinculada a los datos.
    3. **ngDoCheck**: Este es para la detección y para actuar sobre los cambios que Angular no puede o no detecta por si solo.
    4. **ngAfterContentInit**: Es llamado después de que el contenido (ng-content) es proyectado en la vista. Se define para manejar cualquiera tarea de inicialización adicional.
    5. **ngAfterContentChecked**: Se llama después de que la detección de cambios predeterminada haya completado la comprobación de todo el contenido (ng-content) de un directive.
    6. **ngAfterViewInit**: Se llama después de que Angular haya inicializado completamente la vista de un componente y las vistas secundarias. Se define para manejar cualquiera tarea de inicialización adicional
    7. **ngAfterViewChecked**: Se llama después de que la detección de cambios predeterminada haya completado la comprobación de cambios en la vista de un componente.
    8. **ngOnDestroy**: Esta es la fase de limpieza justo antes de que Angular destruya el directive/component.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

11. ### ¿Que es enlace de datos o data binding?
    
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

12. ### ¿Que son los metadatos o metadata?

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

13. ### ¿Que es un service?

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

14. ### ¿Cual es la diferencia entre el constructor y ngOnInit?

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

15. ### ¿Que es Dependency Injection en Angular?

    Dependency Injection (DI), es un muy importante patrón de diseño de aplicaciónes en el que una clase pide dependencias de una fuente externas en vez de crear por si misma. Angular viene como su propio framework DI, para solucionar dependencias (servicios u objetos que una clase necesita para realizar su función). Se puede tener servicios que dependen de otros servicios atrevés de toda la aplicación.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

16. ### ¿Cuales son los tipos de Directives que existen?

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

17. ### ¿Cual es el propósito de async pipe?

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

18. ### ¿Cual es el propósito del directive ngFor?

    En Angular se usa ngFor en un template para mostrar cada item de una lista. Por ejemplo, si se quiere iterar en la lista de usuarios

    ```html
    <li *ngFor="let user of users">
      {{ user }}
    </li>
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

19. ### ¿Cual es el propósito del directive ngIf?

    En ocaciones la aplicación necesita msotrar una vista o una parte de la vista solo si ocurre una circunstancia especifica. En Angular ngIf inserta o quita un elemento basandose en una condicion verdadera/falsa. Por ejemplo, si queremos mostrar un mensaje cuando la edad del usuario es mayor a 18.

    ```html
    <p *ngIf="user.age > 18">You are not eligible for student pass!</p>
    ```

    **Nota:** Angualr no esta mostrando y escondiendo el mensaje. Esta agregando y quitando el elemento `<p>` del DOM. Esto mejora rendimiento, en especial con grandes proyectos con muchos data binding.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

20. ### ¿Que es interpolación?

    Es una sintaxis especial que Angular convierte en property binding. Esta una alternativa conveniente a property binding. Esta representado por doble llaves `{{ }}`. El texto entre las llaves normalmente es el nombre de una propiedad de componente. Angular reemplaza ese nombre con la string del valor que la propiedad del componente correspondiente.

    Por ejemplo:

    ```html
    <h3>
      {{title}}
      <img src="{{url}}" style="height:30px">
    </h3>
    ```

    Angular evalúa las propiedades `title` y `url` y llena los espacios en blanco, primero mostrando el title y luego el URL.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

21. ### ¿Que son template expressions?

    Un template expression produce un valor similar a cualquier JavaScript expression. Angular ejecuta la expresión y le asigna a una propiedad de un binding target. El target podría ser un elemento HTML, un componente, o un directive. En el property binding, un template expression aparece del lado derecho del símbolo `=` en comillas de las siguiente manera `[property]="expression"`. En interpolation syntax, el template expression es envuelta en doble llaves. Por ejemplo, en la siguiente interpolación, el template expression es {{username}}

    ```html
    <h3>{{username}}, welcome to Angular</h3>
    ```

    Las siguientes JavaScript expression están prohibidas en template expressions:

    1. Asignaciones (`=`, `+=`, `-=`, `...`)
    2. `new`
    3. Chaining expressions con `;` o `,`
    4. Incremento o decremento (`++` y `--`)

    **[⬆ Ir Arriba](#tabla-de-contenido)**

22. ### ¿Que son template statements?

    Un template statement responde a un event provocado por binding target, como un elemento, componente o directive. Los template statements aparecen entre comillas al lado derecho del símbolo `=` como `(event)="statement"`.

    Por ejemplo, un click event en un botón

    ```html
    <button (click)="editProfile()">Edit Profile</button>
    ```

    La siguientes JavaScript expressions no son permitidas:

    1. `new`
    2. Incremento o decremento (`++` y `--`)
    3. Operaciones de asignación (`=`, `+=`, `-=`)
    4. Operadores bitwise (`|` y `&`)
    5. Los operadores de template expressions

    **[⬆ Ir Arriba](#tabla-de-contenido)**

23. ### ¿Como se categorizan los tipos de data binding?

    Los binding types puede agruparse ene 3 categorías distinguido por la dirección en que los datos fluyen.

    1. source-to-view
    2. view-to-source
    3. view-to-source-to-view

    | Data direction                    | Syntax                                                       | Type                                             |
    | --------------------------------- | ------------------------------------------------------------ | ------------------------------------------------ |
    | From the source-to-view (One-way) | 1. {{expression}} <br />2. [target]="expression" <br/> 3. bind-target="expression" | Interpolation, Property, Attribute, Class, Style |
    | From view-to-source (One-way)     | 1. (target)="statement" <br/>2. on-target="statement"        | Event                                            |
    | View-to-source-to-view (Two-way)  | 1. [(target)]="expression" <br/>2. bindon-target="expression" | Two-way                                          |

    **[⬆ Ir Arriba](#tabla-de-contenido)**

24. ### ¿Que son los Pipes?

    Un pipe acepta datos como entrada y la transforma al diseño que deseamos. Por ejemplo, vamos a tomar un pipe para transformar la propiedad `birthday` de un componente en una dato mas human-friendly

    ```ts
    import { Component } from '@angular/core';
    
    @Component({
      selector: 'app-birthday',
      template: `<p>Birthday is {{ birthday | date }}</p>`
    })
    export class BirthdayComponent {
      birthday = new Date(1987, 6, 18); // June 18, 1987
    }
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

25. ### ¿Que son Pipes Parametrizados?

    Un pipe puede aceptar cualquier numero parámetros opciones para afinar el output. El parametrized pipe puede ser crear declarando el nombre del pipe seguido de dos puntos (`:`) y luego el valor del parámetro. Si el pipe acepta varios parámetros, se separan con dos puntos (`:`)

    ```ts
    import { Component } from '@angular/core';
    
    @Component({
      selector: 'app-birthday',
      template: `<p>Birthday is {{ birthday | date:'dd/MM/yyyy'}}</p>` // 18/06/1987
    })
    export class BirthdayComponent {
      birthday = new Date(1987, 6, 18);
    }
    ```

    **Nota:** El valor de parámetro puede ser cualquier template expression valido, tales como un string literal o una propiedad de componente.

    **[⬆ Ir Arriba](#tabla-de-contenido)**

26. ### ¿Como se encadenan los pipes?

    Se pueden encadenar varios pipes en combinaciones potencialmente útiles. Si usamos el ejemplo anterior sobre birthday

    ```ts
    import { Component } from '@angular/core';
    
    @Component({
      selector: 'app-birthday',
      template: `
    		<p>Birthday is {{  birthday | date:'fullDate' | uppercase}} </p>` 
      	// THURSDAY, JUNE 18, 1987
    })
    export class BirthdayComponent {
      birthday = new Date(1987, 6, 18);
    }
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

27. ### ¿Que es un custom pipe?

    Aparte de los que vienen con Angular, podemos escribir nuestros propios pipes con las siguientes características

    1. Un pipe es una clase decorada con un pipe metadata `@Pipe`, la cual se importa desde el core de la librería de angular.

       ```ts
       @Pipe({name: 'myCustomPipe'})
       ```

    2. La clase pipe implementa un interface **PipeTransform** --- que acepta un valor input seguido de parámetros opcionales y retorna el valor transformado. La estructura de **PipeTransform** seria la siguiente

       ```ts
       interface PipeTransform {
         transform(value: any, ...args: any[]): any
       }
       ```

    3. El decorador `@Pipe` te permite definir el nombre del pipe que se usara dentro de las template expressions. Debe ser un JavaScript identifier valido.

       ```ts
       template: `{{someInputValue | myCustomPipe: someOtherValue}}`
       ```

       **[⬆ Ir Arriba](#tabla-de-contenido)**

28. ### Ejemplo de custom pipe

    Se puede crear un pipe personalizado y reusable para transforma valores existentes. Por ejemplo, el siguiente custom pipe entrar el tamaño del archivo en función de una extension

    ```ts
    import { Pipe, PipeTransform } from '@angular/core';
    
    @Pipe({name: 'customFileSizePipe'})
    export class FileSizePipe implements PipeTransform {
      transform(size: number, extension: string = 'MB'): string {
        return (size / (1024 * 1024)).toFixed(2) + extension;
      }
    }
    ```

    Ahora se puede usar este pipe en el siguiente template expression

    ```js
    template: `
    	<h2>Find the size of a file</h2> 
    	<p>Size: {{288966 | customFileSizePipe: 'GB'}}</p> 
    `
    ```

    **[⬆ Ir Arriba](#tabla-de-contenido)**

