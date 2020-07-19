# Angular Preguntas y Respuestas

### Tabla de Contenido

| No. | Preguntas                                                                                            |
| --- | ---------------------------------------------------------------------------------------------------- |
| 1   | [Que es Angular?](#que-es-angular)                                                                   |
| 2   | [Cual es la diferencia entre AngujarJS y Angular?](#cual-es-la-diferencia-entre-angujarjs-y-angular) |
| 3   | [Que es TypeScript?](#que-es-typescript) |

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
