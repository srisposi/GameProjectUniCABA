Commit 1 - HTML & CSS Setup

Commit 2 - JavaScript Setup

1. Creamos el addEventListener, mediante el cual se carga en la ventana, todo el objeto de javascript.

LOAD EVENT: El evento de carga se activa cuando se ha cargado toda la página, incluidos todos los recursos dependientes, como la hoja de estilo y las imágenes.

Necesitamos hacer esto porque, como utilizaremos muchos gráficos (puede tardar en cargar). Recordar que javascript recién corre cuando tiene la imagen cargada.

AddEvenListener: https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener

A continuación comenzamos a definir nuestras primeras variables:

1. canvas: Es el lienzo donde tendremos nuestro gráfico. Tiene que estar cargado toatalmente nuestro lienzo
   antes de correr el código. Por eso una la variable canvas hacemos referencia al elemento del canvas.

2. ctx: Drawing Context: Contexto de dibujo es un objeto integrado que contiene todos los métodos y propiedades que nos permiten dibujar y animar colores, formas y otros gráficos en el lienzo HTML.

En esta variable necesitamos llamar un método especial que es el de getContext() el cual mantiene la referencia en el elemento de canvas. Le paso a este método un identificador que en este caso será "2d". A veces necesitamos llamar a este argumento un tipo de contexto, podemos pasarle 2d o webgl. Entendiendo que webgl representa un contexto de renderizado de tres dimensiones, para nuestro caso, trabajaremos con un contexto de 2d.

more: https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext

Terminado estás definiciones puedo acceder a las propiedades del canvas, como son el ancho y el alto y definirlos.

más acerca de canvas: https://developer.mozilla.org/es/docs/Web/API/Canvas_API/Tutorial

Commit 3 - Object Oriented Programming With JavaScript
POO: lo que significa que envolveremos variables y funciones en objetos

Javascript es un lenguaje orientado a objetos basado en prototipos, lo que significa que no tiene clases, tiene prototipo, pero puede usar la sintaxis js moderna que introdujo clases como el llamado azúcar sintáctico (sintaxis limpia simplificada que imita las clases de otros lenguajes de programación).
Todavía bajo el capó, solo funciona con herencia basada en prototipos.

Uno de los principios de la POO es la encapsulación: Es la agrupación de datos y los métodos que actúan sobre esos datos en objetos. El acceso a esos datos se puede restringir desde fuera del paquete.
El desafío con este concepto es ver como las clases se comunican entre sí.

Necesitamos colocar las clases en el orden específico. Necesito definir primero las clases que voy a utilizar después por hositing?

Para nuestro proyecto tendremos las siguientes clases:

InputHandler: Esta clase la necesito usar dentro de la clase Player. La clase "Manejador" hará un seguimiento de las entradas de usuario especificadas, por ejemplo, las teclas de flecha.

Projectile: Manejará los lasers del jugador.

Particle: La clase de partículas se ocupará de la caída de tornillos y pernos que provienen de enemigos dañados.

Player: Controlará al personaje principal que estará animado con una hoja de sprites.

Enemy: será el manejador principal del plano "blueprint" de muchos diferntes enemigos.

Layer: Manejará de manera individual a los backgrounds en capas que se manejara con parallax que se desplaza sin problemas por el fondo de varias capas.

Background: La clase de fondo juntará todos los objetos de capa para animar todo el mundo del juego.

UI: Esta clase dibujará el puntaje, el tiempo y otra información que necesita ser mostrada para el usuario.

Game: Esta clase tendrá toda la lógica, será el cerebro de nuestro proyecto.

Commit 4 - Creating Player and Game objects

Constructor: Es un método especial en la clase javascript. Cuando llamo a esta clase de javascript más tarde usando la palabra clave "new", el constructor creará un nuevo objeto de javascript en blanco y le asignará propiedades y valores según el plano interno.
