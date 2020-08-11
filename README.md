# Universidad de las Fuerzas Armadas ESPE
# Arquitectura de Computadoras
## Trabajo Extra 

### Dilan  Zurita 

# Tutorial para programación Arduino mediante Visuino, para controlar un LCD

### 1.Planteamiento del problema 
Se desea lograr programar en la placa Arduino mediante la herramienta llamada Visuino con el fin de poder controlar un LCD a nuestro antojo 
### 2.	Objetivos 
•	**General:**
Lograr generar código de programación a través de Visuino, el cual nos permita controlar nuestra placa Arduino conectada a un LCD 

•	**Específicos** 
1.	Lograr que el código se llegue a compilar en la aplicación oficial de Arduino 
2.	Identificar el funcionamiento de la herramienta Visuino 
3.	Analizar las ventajas que posee programar en Visuino 


### 4.	Marco Teórico 

**¿Qué es visuino?** 
 
 ![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/1.png) 
 

Visuino es un ambiente de programación basado en la tecnología Open Wire, en donde todo es conectado por una serie de diagramas y pines, así consigues tener un diseño de tu circuito electrónico con su correspondiente código para grabarlo en Arduino.

En pocas palabras: haces  un circuito electrónico con los componentes disponibles en Visuino (displays, leds, botones, etc) y entonces Visuino te crea el código para que el circuito te funcione, con tu placa de Arduino.

**Ventajas** 
Visuino incorpora bastantes cosas positivas como la preselección de la placa Arduino con la que desarrollaremos, la selección de componentes que cargaremos y la creación del programa según diagramas lo que nos permite ir más rápidos con la creación de nuestros programas.
Algunos versiones de Visuino también nos permite editar el código fuente directamente desde la herramienta, como también posee una consola en la cual se puede simular lo que hemos creado.

**Desventajas**
Esto está muy bien, pero Visuino aún no llega al IDE oficial de Arduino. Por un lado Visuino sólo está disponible para Windows, frente las otras plataformas para las que el IDE de Arduino si que está. 

Además Visuino (full) es de pago, algo que no ocurre con el IDE de Arduino. La empresa que ha creado Visuino se llama Mitov Software, una empresa que si bien apoya al proyecto Arduino, no es una empresa oficial por lo que a la hora de programar no es lo mismo que el IDE de Arduino que si es oficial.

**Entorno de Visuino y componentes** 

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/2.png)

Visuino al ser un entorno de programación grafica cuenta con grandes propiedades para que al usuario le sea posible llevar a cabo sus proyectos. Su entorno luce de la siguiente manera, con la peculiaridad de darnos una placa Arduino precargada cada vez que ejecutemos la aplicación.
 

Sus diferentes componenetes y las características que nos ofrece serán explicadas a continuación:

-	En su parte superior contamos con una barra peculiar de herramientas.

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/3.png)
 

En esta barra si seguimos el orden de izquierda a derecha, tenemos propiedades con las cuales podemos:
1.	Crear un nuevo proyecto
2.	Cargar un archivo 
3.	Guardar nuestro progreso 
4.	Mostrar las líneas de referencia (reglas)
5.	Mostrar el fondo punteado de referencia 
6.	Retroceder y avanzar 
7.	Ampliar o minimizar (zoom)
8.	Organización automática 
9.	Habilitar o deshabilitar nuestro circuito de forma automática 
10.	Eliminar lo seleccionado 
11.	Enviar nuestro proyecto al IDE de Arduino para que se pueda crear el código fuente 
12.	Cargar a la placa Arduino directamente 
13.	Cambio de tema Claro/Oscuro 

**¿Qué es un LCD?**

Las siglas LCD significan “Liquid Cristal Display” ó pantalla de cristal líquido. Es una pantalla plana basada en el uso de una sustancia liquida atrapada entre dos placas de vidrio, haciendo pasar por este una corriente eléctrica a una zona especifica, para que así esta se vuelva opaca, y además cuenta (generalmente) con iluminación trasera.
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/4.jpg)	

**Características de un LCD**

En este caso, usaremos un LCD 16x2 por lo cual se mencionaran características generales de un LCD y especificas de un 16x2.

**Generales:** 
-	Tamaño:
El tamaño de un panel LCD generalmente se mide a lo lardo de su diagonal, expresado generalmente en pulgadas. Sin embargo existen más características que pueden describir las dimensiones aproximadas, como por ejemplo la LCD 16×2 (negro sobre fondo azul) se refiere a que tiene la capacidad de tener al mismo tiempo 16 caracteres de manera horizontal en dos renglones (cada uno).
-	Resolución:
Esta se expresa con las dimensiones horizontal y vertical. las pantallas HD tienen una resolución de 1920×1080 por ejemplo. Y esta puede alcanzar con esta resolución una gran variedad de tamaño, pero si no se ocupa gran a gran detalle esta, estarías desperdiciando calidad (por no utilizar algo que tienes disponible). En 5hz se maneja, por ejemplo la LCD gráfica 128×64 (negro sobre fondo verde). Que a pesar de su tamaño la consideramos suficiente para las aplicaciones estudiantiles, y algunas industriales donde se requiera tener algo claro y legible en un tamaño práctico.
-	Brillo:
La luminosidad de la pantalla también es importante analizarla, ya que según la aplicación en la que se encuentre esta, requerirá más luz para poder apreciarse, o viceversa. Por lo que la mayoría cuentan con una luz trasera y la posibilidad de poder controlar su luminosidad.
-	Iluminación CCFL:
Esta iluminación básicamente consta poner detrás de la pantalla una matriz de CCFL, o bien en las orillas o bordes de la pantalla. Sin embargo es más consumo que el led y tiene un menor tiempo de vida, por lo que poco a poco se ah ido poniendo en segundo plano.
-	Iluminación LED: 
Esta iluminación puede presentarse en dos maneras, en un solo color, (generalmente blanco) o bien en RGB, los blanco suelen ser los más utilizados. Estos al igual que la iluminación CCFL, pueden estar formando una matriz en la parte de atrás, o bien pueden colocarse a los extremos del display.
-	Contraste:
Es la relación entre la intensidad más brillante y la más oscura.
-	Angulo de visión: 

Es el ángulo máximo en el que el usuario puede visualizar lo que está en la LCD sin que se pierda mucha calidad.


**Específicas:** 
-	16 caracteres x 2 líneas
-	Caracteres de 5x8 puntos
-	Tamaño de caracter: 5.23 x 3 mm
-	Puede mostrar letras, números, caracteres especiales, y hasta 8 caracteres creados por el usuario
-	Backlight de LED color azul
-	Caracteres color blanco
-	Interface paralela. Puede operar en modo de 8 bits, o de 4 bits para ahorrar pines del microcontrolador
-	Posee controlador KS0066U o equivalente on-board (compatible Hitachi HD44780)
-	Voltaje de alimentación: 5 V

**Pines del LCD 16x2**
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/5.png)

### 5.	Diagramas 

En el siguiente diagrama se puede apreciar como se ha realizado la conexión del Arduino con el LCD en la herramienta de Visuino.
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/6.png)

-	Razón de las conexiones 
En el presente diagrama se ha usado los pines 1,2,4,5,6,7

**Pines 1 y 2** 
En este caso los pines del Arduino son conectados con los dos de los pines mas importantes para el funcionamiento del LCD, los cuales son:
**Pin RS: Selección de Registro.**
0 lógico: Registro de comandos (escritura),
1 lógico: Registro de datos (escritura, lectura)
**Pin Enable:** El famoso Enable de casi todos los componentes de la electrónica digital. Un 1 lógico señala el inicio de escritura o lectura del LCD, un 0 lógico, desactiva todas las funciones.
Por otro lado tenemos el **Pin R/W** el cual no se ha tomado en cuenta ya que queremos que nuestro LCD nos sirva como formato de escritura.
**Pin  R/W:** Escritura y Lectura 
0 lógico: Escritura del LCD.
1 Lógico: Lectura del LCD.   

**Pin 4,5,6,7:** Son pines simples, de entrada de datos, se ordenan del más significativo al menos significativo.

### 6.	Lista de Componentes 

Para poder realizar este proyecto se necesitan los siguientes componentes:

•	Aplicación de Arduino 
•	Instalar Visuino 
•	Montaje del circuito para probar el programa (arduino, LCD 16x2, cables, capacitor, protoboard), en caso de no tener los instrumentos físicos se puede simular el circuito en Tinkercad o en un programa de su agrado.

### 7.	Descripción de prerrequisitos 
Antes de comenzar con cualquier procedimiento debemos tener en cuenta estos dos prerrequisitos:
•	Trabajar sobre Windows, ya que visuino solo está disponible para este sistema operativo
•	Instalar la librería “OneWire” ya que visuino trabaja con esta librería 
### 8.	Tutorial

Para poder controlar nuestro LCD mediante Arduino hay que generar un programa el cual lo vamos a construir por medio de visuino, y para esto necesitamos seguir los siguientes pasos:
1.	Se debe instalar Visuino, y lo haremos desde la pagina https://www.visuino.com/ , donde descargaremos esta versión.
 
2.	Una vez que se haya instalado correctamente Visuino, vamos a buscar los componentes con los que vamos a trabajar.
-	Placa Arduino
Arduino Uno vine precargado por defecto en la herramienta de Visuino, sin embargo se podría cambiar a diferentes versiones de Arduino dando click derecho sobre el nombre arduino uno donde se nos deplegara las opciones, en este caso lo dejamos en Arduino Uno
 
 ![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/7.png)

-	LCD de 16x2
Este componente lo podemos encontrar en el grupo de displays en la parte derecho superior de Visuino.

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/8.png)

Dentro de esta categoría vamos a encontrar el LCD 16x2
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/9.png)

3.	Una vez seleccionados los componentes vamos a tener a disposición sus entradas y salidas, con el fin de conectarlas según queramos que se interprete las funciones del LCD mediante el Arduino, entonces se presentaran los componentes de esta manera.

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/10.png)
 
Con lo cual ya podemos trabajar y vamos a proceder a hacer las conexiones correspondientes.
-	Register Select
Esta pin del LCD lo vamos a conectar al pin Digital número 1 de Arduino ya que este solo necesita valores de 1 o 0 para registrar datos y comandos o solo datos respectivamente.

 ![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/11.png)

-	Enable 
El pin enable se lo conectara al pin 2 digital del Arduino ya que de igual manera solo necesita de un 1 o 0 para operar.
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/12.png)
-	Data pins 
Los data pins que vamos a usar son los 4,5,6,7 los cuales son los 4 bits menos significativos, y los conectamos a los pines del mismo orden (4,5,6,7) en la placa arduino.
 
 ![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/13.png)

4.	Una vez que la conexión de nuestros componentes este realizada, vamos a ingresar los datos que queremos que se representen en la pantalla del LCD, para esto nos vamos a dar doble click en el nombre del componente donde se nos desplegara esta pantalla.
   
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/14.png)

En esta pantalla vamos a elegir la opción de text field dándole doble click, y de la misma manera vamos a generar otra, dando como resultado lo siguiente.

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/15.png)
 
5.	Una vez que hayamos creado nuestros apartados para ingresar los datos, tenemos que tener en cuenta el orden que maneja un LCD, representado en el siguiente grafico.
 
 ![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/16.jpg)

Una vez que tenemos claro el orden que se maneja en un LCD procedemos a ingresar el mensaje que queremos ver el nuestro LCD con su respectiva ubicación 
-	Text Field 1 
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/17.PNG)

-	Text field 2 
 
 ![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/18.PNG)

6.	Una vez que culminanos con el ingreso y ubicación de datos, ya estamos listos para poder generar el código, y para esto vamos a darle click en la parte superior de Visuino, en el icono de Arduino.
 
![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/19.png)

Una vez presionado el botón Visuino se encargara de generar el código fuente en la aplicación de Arduino.

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/20.png)
 
Con los pasos descritos se podrá generar código mediante visuino para diferentes proyectos que ya quedan a libertad del programador.

### 9.	Conclusiones 
Después del respectivo proceso antes realizado, podemos concluir que si se pudo generar codigo de programacion a traves de la herramienta de Visuino el cual nos ayudo a controlar nuestro LCD, además que nos facilito el programar sobre el.
Con estos resultados podemos determinar que la herramienta de Visuino es de gran ayuda debido a la ventaja en cara al ahorro de tiempo que representa al momento de programar, lo cual nos indica que le podemos sacar mayor provecho si se la estudia y trabaja a fondo.

### 10.Aportaciones
Como un aporte a este proyecto, se ha diseñado el circuito sobr el cual se necesita correr el programa que se ha trabajado.
Para esto se ha usado la herramienta TinkerCad, y el circuito realizado se lo presenta a continuación.

![](https://github.com/dilanzurita/Tutorial-LCD-con-visuino-/blob/master/Img/circuito.PNG)

### 11.Bibliografía
Tutoriales Electronica, Kit electronica (2015), recopilado de:[link 1](https://www.kitelectronica.com/2015/06/visuino-entorno-grafico-para-programar.html#:~:text=Visuino%20es%20un%20ambiente%20de,c%C3%B3digo%20para%20grabarlo%20en%20Arduino.)
