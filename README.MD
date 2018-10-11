# Tests de comportamiento con Gherkin y Cucumber

## ¿Porque tests de comportamiento?
Los test de comportamiento nos permiten probar nuestro sistema en un nivel un poco más amplio. Mientras que los test unitarios nos dejan probar cosas puntuales, los de funcionamiento nos permiten probar casos de uso o _user stories_ de manera integral.

Al tener una buena cobertura de nuestro sistema nos encontramos con que generamos lo siguiente:
* **Confianza:** sabemos que si algo sale mal los test nos lo van a hacer saber y podemos deshacer lo que haya salido mal.
* **Refactor seguro:** Sobre la base de la confianza ganada, podemos hacer casi cualquier refactor que se nos ocurra, sabemos que si los test dan bien no vamos a haber roto nada; y si aún así falla, estamos siempre a un rollback de distancia de la tranquilidad
* **Nuevos features seguros:** Otra ventaja que se desprende de la confianza es la posibilidad de generar nuevos features seguros, que no van a romper con el desarrollo previo, y si lo hacen, los tests darán la alarma y nuevamente podemos volver atrás con lo que falle

### ¿Pero cómo podemos implementar esto?
No es necesario que tengamos un proyecto realizado 100% con TDD y/o BDD, podemos generar test de comportamiento siguiendo ciertas premisas basicas de la metodologia SCRUM, sobre todo en lo que se refiere a las _user stories_

### ¿Que son las _user stories_?
Las _user stories_ son pequeñas y simples descripciones de caracteristicas del sistema explicadas en primera persona por quien desea la nueva funcionalidad.
Generalemente siguen un patron comun:

```
Como <tipo de usuario>, quiero/necesito <funcionalidad esperada>, para <razon para la que solicita la funcionalidad>
```

Se suelen escribir en notitas adhesivas, y se distribuyen en paredes o tableros para poder visualizar, planear y discutir el curso a seguir para las características y/o funcionalidades.


#### Escribiendo _user stories_
Las _user stories_ pueden abarcar desde un amplio aspecto de una gran funcionalidad hasta tareas mas especificas.
A las grandes _user stories_ se las refiere como _epic_ (epicas). Como este tipo de _user stories_ suelen ser muy grandes se suele subidividr en _user stories_ mas pequeñas que pueden completarse en una iteracion del proceso de desarrollo.

Por ejemplo:

_**Como** usuario, **quiero** copiar todo mi disco rigido (epic)_


Esta epic user story se puede dividir en docenas de _user stories_ mas pequeñas, como por ejemplo:

* _**Como** usuario avanzado, **quiero** especificar que archivos copiar_
* _**Como** usuario, **quiero** indicar que archivos no copiar cuando el disco no este lleno_

Para agregar detalle a las _user stories_, se pueden dividir en _user stories_ mas pequeñas, se les puede agregar condiciones de realizado (_Definicion de Hecho_)
Asi, como un poco mas de detalle tendriamos _user stories_ de este tipo:

_**Como** vice presidente de marketing, **quiero** evaluar una temporada de fiestas como reseña de la performance de campañas de publicidad anteriores, **para** poder indentificar las mas rentables_

Como detalle extra podriamos agregar en la definicion:

&nbsp;&nbsp;&nbsp;_Asegurarnos que funcione con la mayoría de las principales fiestas: Navidad, Pascuas, dia de la madre, del padre.
Tomar hasta 2 años calendario_

## Plasmado en Gherkin y Cucumber
Esta metodología parece muy buena, pero ¿cómo implemento esto en mi proyecto?
Para esto contamos con 2 herramientas, Gherkin y Cucumber

### Gherkin

Gherkin, es un lenguaje comprensible, que vamos a usar para describir funcionalidades, definiendo el comportamiento del software, sin entrar en la implementación. Es fácil de leer y entender. Además nos permite crear la documentacion en conjunto con las pruebas de comportamiento. Más interesante aún, es que soporta varios idiomas ademas del inglés.

Para empezar basta con conocer 5 palabras basicas:

* _**Feature**_: Indica el nombre de la funcionalidad que vamos a probar. Debe ser un título claro y explícito. Incluímos aquí una descripción en forma de historia de usuario: “Como [rol ] quiero [ característica ] para que [los beneficios]”. Sobre esta descripción empezaremos a construir nuestros escenarios de prueba.
* _**Scenario**_: Describe cada escenario que vamos a probar.
* _**Given**_: Provee contexto para el escenario en que se va a ejecutar el test, tales como punto donde se ejecuta el test, o prerequisitos en los datos. Incluye los pasos necesarios para poner al sistema en el estado que se desea probar.
* _**When**_: Especifica el conjunto de acciones que lanzan el test. La interacción del usuario que acciona la funcionalidad que deseamos testear.
* _**Then**_: Especifica el resultado esperado en el test. Observamos los cambios en el sistema y vemos si son los deseados.

Así pasamos nuestras _user stories_ a pruebas automatizadas, que podremos ejecutar con la ayuda de Cucumber


### Ejemplos
[...]



## Lectura recomendada
https://www.mountaingoatsoftware.com/agile/new-to-agile-or-scrum

https://www.mountaingoatsoftware.com/agile/user-stories

https://martinfowler.com/bliki/GivenWhenThen.html

https://martinfowler.com/bliki/TestDrivenDevelopment.html
