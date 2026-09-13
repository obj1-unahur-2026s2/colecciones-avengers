# Avengers y el Chasquido de Thanos

### Pautas para la resolución del ejercicio
Desarrollar la solución en los archivos:
- avengers.wlk
- heroes.wlk
- thanos.wlk
- testAvengers.wtest

No realizar cambios en los nombres de los archivos, ya que las correcciones solo tienen en cuenta los objetos modelados en los mismos. 
Respecto a los nombres de objetos y nombres de mensajes a utilizar en el modelado, remitirse al **glosario** de "nombres obligatorios" que está al pie de este documento (respetar mayúsculas y minúsculas). Tener en cuenta que los métodos SIEMPRE tienen paréntesis, y a veces pueden tener parámetros y otras veces no. Si en la solución no se utilizan los nombres indicados en el glosario, los test de las correcciones podrían no funcionar y restan puntos de la calificación. Tener en cuenta que pueden definir métodos y objetos auxiliares de ser necesario.

## Enunciado

Los Vengadores deben prepararse para enfrentar a Thanos, una amenaza cósmica capaz de poner en peligro a todo el Universo. El equipo está formado por Iron Man, Black Widow, Hulk y Dr. Strange.

## Los héroes
Los héroes tienen distintas características que determinan su poder de combate y también todos nos deben poder decir su nombre. Además, durante la batalla pueden ocurrir situaciones que modifiquen la composición y el poder del equipo.

- **ironMan** tiene un poder base de 600 unidades y una energía que comienza en 100. Su poder de combate es la suma de su poder base y su energía actual. La energía nunca puede ser mayor que 100 ni menor que 0. 

- **blackWidow** tiene un poder de combate de 400 unidades si está viva, si no es cero. Inicialmente está viva, pero como consecuencia de una batalla puede morir.

- **hulk** puede encontrarse como Bruce Banner o transformado en Hulk. Cuando está como Bruce Banner tiene un poder de 100 unidades, mientras que transformado tiene un poder de 800 unidades. Puede cambiar entre ambos estados en el momento que él quiera.

- **drStrange** tiene un poder de 600 unidades y es fundamental para que los Avengers puedan derrotar a Thanos.


## El enemigo 🤨

- **thanos** tiene un poder de 2000 unidades. También entiende el mensaje *talgico()*, que será verdadero mientras Thanos extrañe su antiguo hogar en Titán. Inicialmente lo extraña, pero si hace el chasquido (ver más abajo) deja de extrañar Titan y cambia su estado de ánimo; entonces, si le pasamos el mensaje *talgico()* devolverá falso.

## Avengers 

Al comenzar la historia, todos los héroes forman parte de los Avengers: ironman, blackwidow, hulk (como Bruce Banner) y drStrange (en ese orden). En ese estado, el equipo no tiene suficiente poder para derrotar a Thanos y si le preguntamos puedeDerrotarAThanos() devuelve falso.

Thanos posee el poder del chasquido, un acto devastador que lo transforma todo. 
Cuando ejecuta `hacerElChasquido()`, Dr. Strange es eliminado del universo (junto con el 50% del resto de los seres) y como consecuencia desaparece del equipo de los Avengers. 
El equipo pierde a uno de sus miembros más poderosos, debilitándose significativamente en su capacidad de combate.

Además, al hacer el chasquido, Thanos logra su objetivo final y deja de extrañar a Titán, su antiguo hogar, transformando su estado emocional completamente.

Hulk también sabe revertirElChasquido(), pero hay una condición particular: solo puede hacerlo cuando está como Bruce Banner. Si intenta hacerlo estando transformado en Hulk, no sucede nada. Cuando lo realiza correctamente, Dr. Strange vuelve a formar parte de los Avengers si había sido borrado.


Los distintos personajes deben poder ser tratados de manera polimórfica según los mensajes que compartan.


## Requerimientos Primer parte

avengers conoce quienes son los héroes que forman parte del equipo. Inicialmente están los 4 héroes que mencionamos y se debe poder saber si avengers puedeDerrotar a thanos. Eso será cierto si la suma de los poderesDeCombate de sus héroes es mayor al poderCombate de thanos. Además, se le debe poder pedir a avengers:

- Agregar un héroe.
- Quitar un héroe.
- Agregar varios héroes a la vez.
- Quitar varios héroes a la vez
- Obtener la lista completa de los héroes que están en avengers.
- Saber cuantos héroes tiene actualmente avengers.
- Saber si no hay ningún héroe actualmente en avengers.
- Saber si un héroe dado está presente en avengers.
- Obtener un héroe cualquiera al azar de avengers.
- Obtener el primer héroe (en la lista)
- Obtener el último héroe (en la lista)
- Hacer desaparecer a todos los héroes de avengers.
- Saber el poderDeCombate de un héroe dado si está en la lista, si no devolver 0.
- Saber el poderTotal de avengers (es la suma del poderDeCombate de sus héroes).
- Obtener el héroe de menos poderDeCombate().
- Obtener el héroe de mayor poderDeCombate().
- Obtener la cantidad de héroes con un valor de poder mayor a un valor dado.
- Obtener los nombres de los héroes que están actualmente en avenger. 
- Obtener la lista de los héroes que poseen menos de un valor de poderDeCombate dado.
- Saber si existe al menos 1 héroe que posee un poderDeCombate que está entre un valor mínimo y un máximo.
- Saber si todos los héroes tienen como mínimo un valor de poderDeCombate dado. 
- Ordenar la lista de héroes del de mayor poderDeCombate al de menor poder.
- Calcular el promedio del poder de combate de los heroes que están en avenger.

## Segunda Parte

Ahora nos interesa poder representar cuando avengers ataca a Thanos.
Cuando se le indica a avengers atacarAThanos y puede derrotarlo, thanos muere y a los héroes no les pasa nada. Pero si no pueden derrotarlo, entonces pasa lo siguiente:
- *ironman*: pierde toda su energía (pasa a cero). 
- *blackWidow*: muere.
- *hulk*: se convierte en Bruce Banner.
- *drStrange*: no le pasa nada.
- todos abandonan avengers.

Realizar los cambios necesarios en los objetos para reflejar este comportamiento, y considerar también que si thanos intenta realizar el chasquido estando muerto no pasa nada. También adaptar las condiciones y las consecuencias de revertirElChasquido para que tenga coherencia.

## Pruebas

Implementar los test necesarios para poder probar todo el comportamiento de todos los objetos, incluso cuando se puede ganar la batalla y cuando se pierde. 


---

## Restricciones

Resolver utilizando únicamente los conceptos trabajados hasta el momento:

- objetos;
- mensajes;
- mensajes con parámetros;
- referencias;
- atributos y estado;
- encapsulamiento;
- polimorfismo.
- colecciones

**No utilizar:**

- clases;
- herencia;
- conceptos avanzados que no sean necesarios para resolver el problema.

---

## Consideraciones para el diseño

Agregar nuevos héroes **no debería requerir modificar la lógica de avengers ni de thanos**.

La solución debe modelar el comportamiento del dominio y nada más.

Pueden definir métodos privados, auxiliares o con nombres personalizados según su diseño, siempre que respeten los nombres obligatorios para la autocorrección.

## Glosario de Nombres Obligatorios (Únicamente para Autocorrección)

**Estos son los ÚNICOS nombres de métodos y objetos que están obligados a usar exactamente como aparecen aquí, porque son los que utilizan los tests de autocorrección.**

### Objetos (Obligatorios)
```
avengers
blackWidow
drStrange
hulk
ironMan
thanos
```

### Métodos (Obligatorios)
```
  - atacarAThanos
  - cambiarABruce
  - cambiarAHulk
  - cantidadDeHeroes
  - estaPresente
  - hacerElChasquido
  - noHayHeroes
  - poderDeCombate
  - poderTotal
  - puedeDerrotarAThanos
  - revertirElChasquido
  - talgico
```

**Nota importante:** El resto de la funcionalidad (cómo se agregan/quitan héroes, cómo se aplican las consecuencias de batalla, cómo cambia los estados internos de los objetos, ordenamientos, filtros, promedios, etc.) pueden implementarla con libertad de nombres de métodos, respetando polimorfismo y buen uso de colecciones.

---