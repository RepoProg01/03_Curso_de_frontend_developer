## Que es HTML y CSS ?
* HTML :  Hypertext Markup Lenguage
* CSS : Cascade Style Sheets

## Motores de renderizado de archivos a pixeles
* Chrome = Blink
* Edge = Edge Html
* Safari = Web Kit
* Firefox = Gecko

## Basicamente siguen los siguientes pasos :
* 1 Pasa los archivos  a objetos.
* 2 Calcula el estilo correspondiente a cada nodo DOM ( Document Object Model ).
* 3 Calcula dimensiones de cada nodo y donde van en la pantalla.
* 4 Pinta las diferentes cajas.
* 5 Toma las capas y las convierte en una imagen para mostrar en pantalla.

## CRP Critical Render Path
* 1 DOM ( Document Object Model ).
* 2 CSSOM ( CSS Object Model ).
* 3 Render Tree.
* 4 Layout.
* 5 Paint.

## Sintaxis :
#### Elemento en HTML

* < h1 > --Etiqueta de apertura.
* Hola mundo  --Contenido.
* < /h1 > --Etiqueta de cierre.
```html
<h1> Hola mundo </h1>
```

#### A la etiqueta de apertura se le pueden agregar atributos :

* class = --Atributo
* "title" --Valor
```html
<h1 class="titulo">
```

## Anidamiento :
```html
<section>
    <h1>Titulo</h1>
    <p>parrafo</p>
    <ul>
        <li> lista renglon 1 </li>
        <li> lista renglon 2 </li>
        <li> lista renglon 3 </li>
    </ul>
</section>
```

#### No todas las etiquetas tienen apertura y cierre, algunas solo tienen la apertura y no es necesario su cierre ejemplo :
```html
<img src=" foto.jpg " alt="foto">
```

## Ejemplo de estructura de un archivo HTML :
```html
<!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        Aqui va tu contenido
    </body>
</html>
```

## HTML Semantico :
Nos va a indicar o senalar que tenemos que usar propiedades adecuadas para los textos, parrafos, imagenes etc .
Tenemos que utilizar las differentes etiquetas de HTML que ya existen.

### Ventajas :

* Al hacer esto vamos a lograr tener un codigo accesible.
* Tenemos el tema de posicionamiento SEO.
* Nos permite tener un codigo mucho mas claro, ligero y facil de leer.

## Etiquetas de HTML 
## Layout :
```html
<header> </header>
<nav> </nav>
<section> </section>  
<article> </article>
<aside> </aside>
<footer> </footer>
```

## Textos :
```html
<h1> </h1> ........ <h6> </h6>
<p> </p>
<span> </span>
```

## Formularios :
```html
<form> </form>
<input>
<label> </label>
<button> </button>
```

## Imagenes y video :
```html
<img>
<svg>
<iframe>
<video>
```
## Enlaces :
```html
<a>
```

## Listas :
```html
<ul> </ul>
<li> </li>
<ol> </ol>
```

## Anatomia de una declaracion CSS :

* h1 --Selector.
* { --Llave de apertura.
* color: --Propiedad.
* blue --Valor.
* ; --Punto y coma para cerrar esa linea.
* } --Llave de cierre.

```css
>h1{
    color: blue;
}
```
## Selectores Basicos

## De Tipo :
```css
div {
    ........
    }
```
## De Clase :
```css
.nom_clase {
    ........
    }
```
## De id :
```css
#nom_id {
    ........
    }
```
## De atributo :
```css
a [href=" "] {
    ........
    }
```
## Universal :
```css
* {
    ........
    }
```

## Selectores Combinadores

## Desendentes :

Estos selectores seleccionan elementos que son descendientes de otros selectores. No es necesario que sean hijos directos.
```css
div p
```
## Hijo directo :

El selector de combinación de elementos hijo es un símbolo de «mayor que» (>), que selecciona solo cuando los selectores identifican elementos que son hijos directos. Los elementos descendientes que se encuentran más abajo en la jerarquía no se seleccionan.
```css
div > p
```
## Elemento adyacente :

El selector de elementos hermanos adyacentes (+) se utiliza para seleccionar un elemento que se encuentra justo al lado de otro elemento en el mismo nivel de la jerarquía. 
```css
div + p
```
## General de hermanos :

Si deseas seleccionar los hermanos de un elemento, incluso si no son directamente adyacentes, puedes utilizar el combinador de hermanos general (~).
```css
div ~ p
```
## Selectores Pseudoclases y Pseudoelementos :
## Pseudoclases 
```css
: active
: focus.
: hover
: nth-child (n)
```
## Pseudoelementos
```css
:: after
:: before
:: first-letter
:: place-holder
```

## Cascada y Especificidad
#### En CSS el orden de las reglas si importa se aplican de arriba a abajo, ase que si le cambiamos un color a una clase llamada titulo al principio del archivo, y despues le volvemos a cambiar el color en una linea mas abajo, entonces el color que se mostrara sera el que se uso en la ultima linea, ya que esta ultima sobrescribio la primera.

## Valor :

>- X0 000 = Important.
>- X 000 = Estilos en linea.
>- X00 = ID
>- X0 = Clases y atributos y Pseudoclases
>- X = Elementos y Pseudoelementos.
>- 0 = Seleccion Universal.

#### Ejemplo :

```css
#id h1::first-letter{
    color: blue;
}
```
* id = 100
* h1 = 1
* ::first-letter = 1
>* Total dara = 102

```css
p.clase div:hover{
    color: green;
}
```
* p = 1
* .clase = 10
* div = 1
* :hover = 10
>* total dara = 22

#### Con este ejemplo anterior podremos entender mejor este siguiente :

### archivo HTML :
```html
<div>
    <p class="pClase" id="pId">Parrafo</p>
</div>
```
### Especificidad de (p) con id :
>* Elemento = 1
>* id 100.
>* Total = 101

### Especificidad de (p) con class :
>* Elemento = 1
>* class 10.
>* Total = 11
### archivo CSS :
```css
#pid{
    color: blue;
}
.pclase{
    color: red;
}
```
### El color del parrafo sera de color azul ya que el valor del id es mayor al el valor de la clase, sin importar que en el CSS el orden sea primero el azul y despues el rojo, dando la impresion que el rojo sobrescribiria el azul por el orden en el que estan, pero el azul gana por especificidad.

## Tipos de display :
### Display es el tipo de visualizacion que tienen los elementos :

>* block -- Ocupa el renglon completo.
>* inline -- Ocupa solo el espacio del elemento en el renglon.
>* inline-block -- Puede comportarse como inline o block
>* flex --Layout de forma más reponsive
>* grid --Layout en forma de grilla

## Display flex
Este display nos ayuda a tener un layout de forma más reponsive.

Si un padre tiene display flex sus hijos se van a comportar de forma distinta, similar como si los hijos tuvieran un display inline-block.

Siempre debemos tener un container principal para poder usar esta propiedad de flex.

## flex-direction
Al colocar display flex por default tenemos un display direction en row, esto quiere decir como se van a colocar o acomodar los hijos.

### Tenemos varios valores para esta propiedad

## Row
Coloca a los hijos en forma de fila o hileras, uno al lado de otro.

## Row-reverse
Coloca a los hijos en forma de fila o hileras, uno al lado del otro, pero en forma inversa. El último pasa a ser el primer elemento, todo se recoloca inversamente del lado original.

## Column
Coloca a los hijos en forma de columna o verticalmente, como estaban originalmente antes del display flex como si todos tuvieran display block.

## Column-reverse
Coloca a los hijos en forma de columna, pero de forma inversa. El último elemento pasa a ser el primero elemento, todo se recoloca inversamente del lado original.

## flex-wrap
Esta propiedad no viene implícita y debemos colocar en caso de que la necesitemos.

### Esta propiedad tiene los valores de

## wrap
Hace crecer mi contenedor, basándose en el viewport, va aplicando u ordena a los elementos de forma inteligente.

A medida que mi pantalla es más pequeña el contenido se va a acomodando de arriba abajo.

## wrap-reverse
Realiza lo mismo que el valor wrap, solo que este acomoda el contenido de abajo arriba.

## justify-content
Nos permite alinear el contenido de forma horizontal, en el caso que tengamos el flex-direction que viene por default si lo tengamos en column este va a linar de forma vertical.

## center
Permite alinear el contenido hacia el centro.

## flex-end
Mueve todos los elementos se van hacia la derecha, en caso de que lo tengamos hacia la izquierda.

## flex-start
Este valor viene por default.

Hace que el contenido se mueva hacia la izquierda.

## space-around
Distribuye a los elementos en todo el width dejando un espacio es entre ellos.

Este espacio no es el mismo a lo largo de todo el contenedor, los elementos que se encuentran en los límites laterales del contenedor tienen un espacio menor a comparación del espacio entre los mismos elementos que es mayor.

## space-evenly
Funciona igual que el space-around, pero con una diferencia.

Con este valor el espacio que hay entre todos los elementos y de los que se encuentran en los límites del contenedor son todos iguales.

## flex-flow
Con esta propiedad podemos utilizar a flex-direction y a flex-wrap en la misma línea, separadas por un espacio.

## align-items
Esta propiedad nos permite alinear los elementos de forma vertical, en caso de que tengamos un flex-direction column esta propiedad nos permitirá alinear los elementos de forma horizontal.

Al igual que justify-content tenemos varios valores que nos permiten manejar los elementos de un contenedor.

## center
Alinea los elementos hacia el centro del contenedor.

## flex-end
Coloca los elementos hacia la parte baja del contenedor.

## flex-start
Coloca los elementos hacia arriba del contenedor.

## stretch
Estira hacia el 100% del height, dependiendo el flex-direction, del contenedor a los elementos. Siempre y cuando estos elementos no tengan un height definido.

## baseline
Reduce el height de los elementos hasta el contendido que tienen estos, tan grande o tan pequeño sea el contenido así será el height. Siempre y cuando estos elementos no tengan un height definido.

## align-content
Acepta los mismos valores que align-items.

Esto puede ser confuso, pero align-content determina el espacio entre las líneas, mientras que align-items determina como los elementos en su conjunto están alineados dentro del contenedor. Cuando hay solo una línea, align-content no tiene efecto.

## order
Si tenemos al contenedor con display: flex podemos utilizar una nueva propiedad que es order.

Order no se utiliza en el contenedor padre, sino que se lo coloca a los elementos o hijos. Al usar esta propiedad podemos cambiar el orden de los elementos, haciendo que el primer elemento sea el último, que el último sea el segundo, etc.

Los elementos que no tengan un order se moverán a la izquierda y a partir del último elemento, sin la propiedad order, se va a empezar a contar los elementos que si tengan esta propiedad.

## flex-grow
Cuando nos sobra un espacio, de forma horizontal, y deseamos llenarlo con alguno de los elementos utilizamos esta propiedad.

Al colocarle de valor 1 esta empezará a crecer para ocupar el espacio en blanco que podemos tener y se lo aplica directamente a los hijos no al contenedor o padre.

### archivo HTML :
```html
    <div class="container">
        <div class="item">caja 1</div>
        <div class="item"></div>
        <div class="item"></div>
        <div class="item"></div>
    </div>
```
### archivo CSS :
```css
        .container{
            display: flex;
            gap: 10px;
            background-color: brown;
            justify-content: center;
            align-items: center;
            height: 500px;
        }
        .item{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
        .container > .item:nth-child(odd){
            background-color: blueviolet;
        }
```

### nth:child( )
```css
.container .item:nth-child(odd) o tr:nth-child(2n+1)
```
### Representa los hijos directos impares de un contenedor: 1, 3, 5, etc.
```css
.container .item:nth-child(even) o tr:nth-child(2n)
```
### Representa los hijos pares de un contenedor : 2, 4, 6, etc.

:nth-child(7)
### Representa el séptimo elemento.
```css
.container .item:nth-child(5n)
```
### Representa los items 5, 10, 15, etc.
```css
.container .item:nth-child(3n+4)
```
### Representa los items 4, 7, 10, 13, etc.
```css
.container .item:nth-child(-n+3)
```
### Representa los primeros tres items entre un grupo de hermanos.
```css
p:nth-child(n)
```
### Representa cada elemento <p> entre un grupo de hermanos. Esto es lo mismo que un simple selector p.
```css
p:nth-child(1) o p:nth-child(0n+1)
```
### Representa cada <p> que es el primer elemento entre un grupo de hermanos. Esto es lo mismo que el selector :first-child.
## Grid :
Grid consiste en el ordenamiento de elementos hijos en dos ejes, como si fuera una cuadrícula o tabla. El elemento padre o contenedor deberá contener la propiedad display con el valor grid y debes definir las medidas de las columnas y de las filas. A partir de aquí, ya puedes ordenar los hijos según sea necesario.
### archivo HTML :
```html
    <div class="container">
        <div class="item"></div>
        <div class="item"></div>
        <div class="item"></div>
        <div class="item"></div>
    </div>
```
### archivo CSS :
```css
        .container{
            display: grid;
            width: 600px;
            height: 600px;
            background-color: aquamarine;
            grid-template-columns: 1fr 1fr 1fr 1fr;
            grid-template-rows: 1fr 1fr 1fr 1fr;
        }
        .item{
            background-color: brown;
        }
        .container > .item:nth-child(even){
            background-color: blue;
        }
        .container > .item:nth-child(1){
            grid-column: 1/2;
            grid-row: 1/2;
        }
        .container > .item:nth-child(2){
            grid-column: 2/3;
            grid-row: 2/3;
        }
        .container > .item:nth-child(3){
            grid-column: 3/4;
            grid-row: 3/4;
        }
        .container > .item:nth-child(4){
            grid-column: 4/5;
            grid-row: 4/5;
        }
```
## Modelo de caja :
## Margin
El estilo de margin puede ser un espacio externo de la caja hacia el exterior, es un espacio.

Es un espacio externo del elemento, es como decir la distancia que hay de tu cuerpo hasta tu pantalla o pared que tengas al frente.

## Border
El borde puede estar o no.

Es la o las líneas que bordea un elemento por defecto viene transparente pero nosotros podemos agregarle color y un grosos.

## Padding
Es distinto al margin, ya que el padding no es un espacio externo, sino que es un espacio interno, de la caja hacia adentro.

Nos ayuda a posicionar el contenido de la caja.

## Contenido
Puede ser cualquier cosa que sea visible, ya sea un texto, imágenes, videos, etc.

Dentro de este también tenemos

## Width
Es lo largo o ancho que va a generar que tiene la caja contenedora o el contenido.

## Height
Es el alto que tiene o que queremos que tenga el contenido.

Con esto todo esto podemos jugar con las dimensiones de las etiquetas o del contenido de las mismas.

## Position
También tenemos el position del contenido, que de acuerdo a este podemos jugar con sus posiciones top, right, borrom, left, se lo puede posicionar en cualquiera de estos.

Desglosando el modelo de caja
Si vemos más a profundidad el modelo de caja vemos que

## Margin
Este viene por default es transparente, no se va a ver.

## Color del fondo
Viene por default transparente, se lo puede cambiar si se desea.

## Imagen de fondo
No viene una imagen de fondo, eso se rellena con el contenido como texto, imágenes, etc.

## Relleno
Es el padding que es transparente.

## Borde
Como lo dijimos este también es transparente, y si deseamos le podemos agregar un color y un ancho.

## Contenido
Son las imágenes, videos, texto o cualquier cosa que podamos ver.

## Padding
Podemos agregar padding de esta forma, donde el primer espacio corresponde al padding de arriba y abajo, el segundo espacio corresponde a los de la derecha e izquierda.

Con esto somos específico el tipo de padding queremos agregar.

También tenemos propiedades más específicas como ser top, bottom, left y right que solo agregan estilos en esas partes.

## Box-sizing: border-box
Con esta propiedad y este valor podemos hace un cálculo automático para que el padding y border no se salgan de las dimensiones que queremos para nuestro elemento.

En palabras sencillas mete todo para adentro y realiza el cálculo hacia dentro en vez de sumar espacio al contenido hacia afuera. Lo que hace es restarlo, quitándole espacio al contenido, para que no tengamos problemas con las dimensiones.

Todo esto solo sucede con el padding y con el border, al margin no lo va a recalcular, el margin si crece hacia el exterior.
### archivo HTML :
```html
    <div>
        <h1>ejemplo</h1>
    </div>
```
### archivo CSS :
```css
        div{
            width: 200px;
            height: 200px;
            background-color: aqua;
            padding: 20px;
            box-sizing: border-box;
            border: 1px solid black;
            margin: 20px;
        }
```
## Colapso de margenes :
Las márgenes se colapsan cuando se tienen dos elementos con display block uno debajo del otro. Esto solo ocurre verticalmente.

La superposición no ocurre con elementos con display grid, flexbox, a elementos con posición absoluta o aquellos con un display diferente de block.

También se puede utilizar el valor inline-block de la propiedad display para eliminar el colapso de márgenes.

## Posicionamiento :
Es la forma en la que podemos posicionar los contenedores, cajas o etiquetas de HTML cuando la utilizamos.

Tenemos diferentes position en CSS, pero todas las etiquetas en HTML vienen por defecto con el position static. Se quedan en donde nosotros las ponemos, no se mueve con el scroll.

### Posicionamientos :
* Absolute
* Relative
* Fixed
* Sticky
* Initial
* Inherit

Todos estos nos van a dar un comportamiento diferente por cada una de las etiquetas. Las podemos agregar a todas las etiquetas y nos van a dar el mismo comportamiento pero los vamos a utilizar para diferentes cosas.

## Static
Utilizamos este valor no vamos a tener ningún cambio porque todas las etiquetas vienen con este valor.

Cuando estamos en este position no podemos utilizar las propiedades left, top, right y bottom.

## Absolute
Con absolute el elemento sale de su lugar y el navegador reacomoda los elemento, poniendo otro elemento en el lugar del elemento con position absolute. Podemos posicionar al elemento como queramos.

## Relative
Con relative no sucede lo mismo que absolute, el elemento mantiene su lugar, pero podemos posicionarlo donde queramos.

Lo podemos usar como contenedor para que los elementos que tengan un position absolute tomen como referencia al padre que nosotros queremos (se adhiere al elemento relativo más cercano) y no a otro, delimita el movimiento del hijo.

## Fixed
Este valor de position nos permite que el elemento que queramos nos siga a todos lados desde el momento en el que nos topemos con él.

## Sticky
Es similar a fixed con la diferencia que cuando encuentra a otro elemento con su mismo position, sticky, le da lugar al ese elemento.

## Initial
Vuelve el position de un elemento a como estaba originalmente.

## Inherit
Lo usamos si queremos que nuestro elemento herede el position de su padre.

## Left, top, right y bottom
Con estas cuatro propiedades podemos mover a los elementos que tengan como position a absolute, relative fixed o sticky a los lugares que queramos.

## z index :
Z-index nos permite ajustar el orden de las capas de los objetos cuando el contenido está siendo renderizado.

* El contexto de apilamiento se trata sobre el eje Z, el cual es un eje invisible que va desde la pantalla hacia el usuario.

* Tenemos los diferentes elementos HTML uno encima del otro

* El contexto de apilamiento se puede dar de 2 maneras:

>El orden del HTML importa al momento de crear capas del eje Z, y se da dependiendo del tipo de position del elemento (principalmente absolute)

>Utilizando la propiedad Z-index, esta propiedad solo funciona con determinados tipo de position y nos sirve para “organizar” nuestras capas
* El Z-index respeta el orden y valor de Z-index de los elementos padre

* Si dos elementos tienen position absolute, siempre quedara encima del contexto de apilamiento el elemento que se encuentre “debajo” del otro.
## Propiedades y valores mas comunes en CSS :
#### Layout :
>* display
#### Modelo de caja :
>* margin
>* padding
>* border
#### Size :
>* width
>* height
#### Text :
>* font-size
>* font-weight
>* font-family
>* text-align
>* color
#### Background color :
>* background
>* background-color

## Unidades de medida :

Las unidades se dividen en dos grupos: absolutas y relativas. Básicamente las unidades absolutas definen su valor de forma concreta y determinada, por ejemplo el centímetro.

En cambio las medidas relativas lo hacen tomando otro elemento de referencia y a veces su contexto. En el caso del porcentaje, por ejemplo, cuando se indica sobre el valor width, éste se toma respecto del elemento contenedor.

Es decir que, si tengo un contenedor que mide un ancho máximo de 1000 px y dentro coloco una <div> con un ancho de 25%, esta medida se tomará respecto de los 1000 px del contenedor, por lo tanto, en principio medirá 250px, pero si el contenedor se achica se achicará también.

## Medidas Absoulutas: 
El tamaño no cambiará :

* Px (Píxeles)
* pt (Puntos)
* pc (Picas)
* in (PLugadas)
* cm (Centimetros)
* mm (Milimetros)

## Medidas Relativas: 
El tamaño va a variar :
* rem 
* em 
* vw 
* vh 
* vmin 
* vmax 
* ex 
* ch

REM PARA FONTS y PX PARA LO DEMÁS (WIDTH, HEIGHT, MARGIN, PADDING).

## Unidades de medida relativas
Las unidades de medida en CSS de tipo relativo dependen del elemento o factor al que hagan referencia. Aunque pueden ser inicialmente más complejas, algunos prefieren las unidades de medida relativas porque los tamaños de los elementos dependen el uno del otro. Esto hace que las proporciones entre los elementos se mantengan y todo encaje.

## em
Esta unidad es relativa al tamaño de letra o font size establecida en el navegador. Su nombre es em porque el tamaño de letra se basa en el tamaño de la letra eme. A menos que haya sido modificada por el usuario, normalmente este tamaño es de 16px.

## ex
Esta unidad es relativa a la altura de la «x» del elemento. También se conoce por ser más o menos la mitad del tamaño de la fuente del navegador o 0.5em.

## ch
Conocido en inglés como zero width, esta unidad de medida es relativa al tamaño del ancho del cero en la fuente del navegador.

## %
Esta unidad es relativa al tamaño del elemento padre.

## rem
1 rem = 16px
La unidad rem o root em es similar a la unidad em, pero, en vez de tomar como base el tamaño de letra del navegador, la unidad em toma el tamaño base del documento HTML. Este tamaño se personaliza bajo la etiqueta :root {font-size}. De este modo, podemos usar rem para dimensionar nuestros elementos con un múltiplo del tamaño base.

Esta unidad puede ser muy útil a la hora de dimensionar una página cuando el usuario hace zoom, pues los elementos serán relativos unos a otros y mantendrán su proporción.

## Unidades del viewport
Las siguientes unidades son relativas al viewport, que es el espacio o trozo de pantalla donde se renderiza y se muestra la página web. Estas unidades sirven para dimensionar la pantalla y organizar los elementos dentro de esta.

## vw
Como sigla de la unidad en inglés viewport width, esta unidad es relativa al ancho del viewport.

## vh
Como sigla de la unidad en inglés viewport height, esta unidad es relativa a la altura del viewport.

## vmin
Esta unidad, también conocida como viewport minimum, es relativa al factor que sea más pequeño entre el ancho y al alto del viewport.

## vmax
Esta unidad, conocida como viewport maximum, es relativa al factor que sea más grande entre el ancho y el alto del viewport. Junto con vmin, esta unidad puede ser muy útil si queremos que nuestros diseños sean flexibles y se adapten al tamaño visible de la página web.
### archivo CSS :
```css
        html{
            font-size: 62.5%;
        }
         div{
            font-size: 1.6rem;
            width: 100px;
            height: 100px;
            background-color: aqua;
        }
```
### archivo HTML :
```html
        div{
            font-size: 1.6rem;
            width: 100px;
            height: 100px;
            background-color: aqua;
        }
```

## Responsive design

## ¿Para qué es responsive design?
Es para que nuestro proyecto web pueda ser multiplataforma, que se pueda ver bien en un smartphone, desde una tablet, iPad y que se vean excelente desde una laptop o computadora de escritorio.

Esto realizándolo siempre con buenas prácticas.

Para empezar debemos saber:

## Media Queries
Con los media queries podemos jugar con el layout, cuando la pantalla del dispositivo sea pequeña el contenido se ve de una forma, pero si está pantalla crece el contenido también lo hace sin perjudicar el diseño.

Podemos cambiar la orientación de los contenedores, podemos cambiar su orden, incluso cambiar las dimensiones.

## Breakpoint
Son la dimensión en el viewport, es decir el width y el height de la pantalla, en donde vamos a generar un cambio.

Este cambio es la forma en la que puedo reposicionar ciertos elementos o redimensionar ciertos contenedores, todo esto para que se vea bien la web app y sin importar el dispositivo en el que se abra.

## min-width
Esto quiere decir que cuando la pantalla sea igual o más grande que el valor que coloquemos, el código que esté adentro del media querie se va a ejecutar.

Pero si la pantalla es mayor a ese min-width habrá otro media querie que aplicará estilos diferentes.

## max-width
Esto quiere decir que cuando la pantalla sea igual o más pequeña que el valor que coloquemos, el código que esté adentro del media querie se va a ejecutar.

La mejor forma de aplicar media queries
Tiene de nombre Mobile First o Mobile Only.

Esto quiere decir que el proyecto ya debe estar diseñado para dispositivos mobile, ya no debemos preocuparnos por que se vea bien desde una laptop o computadora de escritorio.

El diseño del proyecto va a partir desde un dispositivo mobile y desde ahí va a ir creciendo a los demás dispositivos con mayor pantalla.

Si hacemos lo contrario de ir de una pantalla grande a una más pequeña, esto se llama solamente responsive design y no es lo que estamos buscando.

Aplicado directo desde CSS con media queries
Arriba de los media queries vamos a tener el código base, que es el que está hecho y optimizado para dispositivos mobile.
Vamos a generar un breakpoint para realizar ciertos cambios en dispositivos más grandes.

Vamos a generar otro breakpoint que va a ser para una tablet o para computadoras con un viewport más pequeño como ser netbooks
Luego vamos a generar otro breakpoint que será para computadoras de escritorio, desktop o dispositivos con pantallas más grandes.
Orden para aplicar los media queries
Partimos desde los dispositivos más pequeños y terminamos con los dispositivos más grandes.

Si lo hacemos de forma inversa tendremos problemas, ya que como CSS funciona en cascada, nunca se van a aplicar los estilos de los medias queries con un viewport más grande.

## Empezamos por:

Los celulares o dispositivos mobile.
Las tablets.
Laptops o computadores de escritorio.

Aplicado directo desde HTML (la mejor practica)
Este método se utiliza, ya que dependiendo del dispositivo donde esté el usuario va a necesitar un archivo CSS u otro, esto es para evitar que carguen archivos que el usuario no va a necesitar ni usar.

Lo agregamos en el head, aquí en vez de ligar un archivo de CSS vamos a ligar más de uno, dependiendo de los dispositivos en los que queramos aplicar los estilos.

## Arquitectura CSS :

¿Qué son y para qué nos sirven las arquitecturas CSS?
Sirven para mantener un orden y una coherencia durante todo el proyecto. Tiene los siguientes objetivos:

* Predecibles: 
>Escribir reglas claras.
* Reutilizable: 
>No escribir código redundante.
* Mantenible: 
>Que sea fácil de leer y adaptable a los estándares.
* Escalable: 
>Que pueda crecer fácilmente sin afectar el rendimiento.

## Estos objetivos se deben ver reflejadas en buenas practicas que debe conocer todo el equipo involucrado en el proyecto como:

* Establecer reglas
* Explicar la estructura base
* Establecer estándares de codificación
* Evitar largas hojas de estilo
* Documentación

## Metodologias CSS :

Las Metodologías o Arquitecturas CSS nos ayudaran a escribir código CSS más predecible, reutilizable, mantenible y escalable.

* OOCSS (Object Oriented CSS)
* BEM (Block Element Modifier)
* SMACSS (Scalable and Modular Architecture for CSS)
* ITCSS
* ATOMIC DESIGN

## OOCSS :
Separacion de la estructura de su piel 

Antes de OOCSS
```css
#button {
  width: 200px;
  height: 50px;
  padding: 10px;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

#box {
  width: 400px;
  overflow: hidden;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

#widget {
  width: 500px;
  min-height: 200px;
  overflow: auto;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
```
Despues con OOCSS
```css
.button {
  width: 200px;
  height: 50px;
}

.box {
  width: 400px;
  overflow: hidden;
}

.widget {
  width: 500px;
  min-height: 200px;
  overflow: auto;
}

.skin {
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
```
Separacion de contenedores y contenido

Sin OOCSS
```css
#sidebar h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 2em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}

/* other styles here.... */

#footer h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 2px 2px 4px;
}
```
Con OOCSS
```css
#sidebar h3, #footer h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 2em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}

#footer h3 {
  font-size: 1.5em;
  text-shadow: rgba(0, 0, 0, .3) 2px 2px 4px;
}
```
## BEM Blocks, Elements and Modifiers (BEM) :
BEM es una abreviatura de los elementos clave de la metodología: Bloque, Elemento y Modificador. BEM significa Modificador de Bloques de Elementos (Block Element Modifier) por sus siglas en inglés. Sugiere una manera estructurada de nombrar nuestras clases, basado en las propiedades del elemento en cuestión. Cuando utilizamos la metodología BEM, hay que tomar en cuenta que solamente podemos usar nombres de clases (no IDs). Los nombres de clases permiten repetir el nombre BEM si es necesario, y crear una estructura de código más consistente (en ambos archivos el HTML y CSS/Saas).

## Scalable and Modular Architecture for CSS (SMACSS)
En el núcleo de SMACSS (Arquitectura en CSS Escalable y Modular) está la categorización. Al clasificar las reglas CSS, comenzamos a ver patrones y podemos definir mejores prácticas en torno a cada uno de estos patrones.
El objetivo principal de esta metodología es reducir la cantidad de código y simplificar el mantenimiento. Para ello, se dividen los estilos en cinco partes:

* Reglas básicas: se establecen los estilos por defectos de los elementos HTML individuales, los típicos selectores CSS de tipo. Por ejemplo:
>reset, html, body, button, h1

* Reglas del layout: se divide la página en secciones y se asignan los estilos relacionados con su estructura.
>header, main content, footer, navigation

* Reglas de módulos: elementos que pueden ser reusables, modulares e independientes del contexto. Por ejemplo: llamadas a la acción o galerías de imágenes.

* Reglas de estados: se define el comportamiento del layout y sus módulos en diferentes estados: hover, active, diferentes resoluciones, etc.

* Reglas de temas: estilos que afectan al layout y módulos. Estas reglas son opcionales, y las puedes utilizar para estilos que puede que quieras reemplazar.

## Scalable and Maintainable CSS Architecture — Xfive

ITCSS es una arquitectura que tiene como principal objetivo estructurar la forma en la que escribimos CSS.

* Configuración : se utiliza con preprocesadores y contiene fuentes, definiciones de colores, etc.

* Herramientas : mixins y funciones de uso global. Es importante no generar ningún CSS en las 2 primeras capas.

* Genérico : restablecer y / o normalizar estilos, definición de tamaño de caja, etc. Esta es la primera capa que genera CSS real.

* Elementos : estilo para elementos HTML desnudos (como H1, A, etc.). Estos vienen con un estilo predeterminado del navegador para que podamos redefinirlos aquí.

* Objetos : selectores basados ​​en clases que definen patrones de diseño no decorados, por ejemplo, objetos de medios conocidos de OOCSS

* Componentes : componentes específicos de la interfaz de usuario. Aquí es donde tiene lugar la mayor parte de nuestro trabajo y nuestros componentes de la interfaz de usuario a menudo están compuestos de objetos y componentes
* Utilidades : utilidades y clases auxiliares con la capacidad de anular cualquier cosa anterior al triángulo, por ejemplo. ocultar clase auxiliar
## Atomic Design
El diseño atómico es una metodología para crear sistemas de diseño. Hay cinco niveles distintos en el diseño atómico:

* Atomos: Los átomos son los componentes básicos de la materia. Aplicados a las interfaces web, los átomos son nuestras etiquetas HTML

* Moleculas: Las cosas comienzan a ponerse más interesantes y tangibles cuando comenzamos a combinar átomos juntos. Las moléculas son grupos de átomos unidos entre sí y son las unidades fundamentales más pequeñas de un compuesto

* Organismos: Las moléculas nos dan algunos bloques de construcción para trabajar, y ahora podemos combinarlas para formar organismos
* Plantillas: En la etapa de plantilla, rompemos nuestra analogía química para entrar en un lenguaje que tenga más sentido para nuestros clientes y nuestro resultado final

* Paginas: Las páginas son instancias específicas de plantillas. Aquí, el contenido del marcador de posición se reemplaza con contenido representativo real para dar una descripción precisa de lo que un usuario finalmente verá