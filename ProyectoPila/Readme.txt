
------Primeros pasos para conversión notación Infija a Postfija.

La notación Postfija es un método algebraico alternativo de introducción de datos que permite reducir el acceso a la memoria del ordenador, sobretodo en calculos masivos y complejos ya que los cálculos se realizan secuencialmente según se van introduciendo los operadores (en vez de tener que esperar a escribir la expresión al completo).
Basicamente consiste en que en una expresión de ese tipo primero están los operandos y después viene el operador. 

Ej:
         "3+5" pasado a notación Postfija seria: "3 5 +" 


------Pasos para la conversión Infijo a Postfijo usando pilas.  

     EXPR = Expresión aritmética notación infija ( Ej: 2*(23+6)-1 )
     E = pila de entrada
     P = pila temporal para los operadores
     S = pila de salida  

1.- Añadir “(” al principio y “)” al final de EXPR. Seguidamente agregar uno a uno todos los parametros de EXPR a la Pila E.
(,2,*,(,23,+,6,),-,1,)

2.- Examinar E de izquierda a derecha y repetir los pasos 3 a 6 para cada elemento de E hasta que esta quede vacía.

3.- Si se encuentra “(”, meterlo en P.

4.- Si se encuentra un OPERADOR (+,-,*,/,^) entonces:

     (a) Repetidamente sacar de P y añadir a S cada operador (de la cima de P) que tenga la misma precedencia o mayor que el operador de E.

     (b) Añadir OPERADOR a P.

[Fin de condicional]

5.- Si se encuentra un “)”, entonces:

     (a) Repetidamente sacar de P y añadir a S cada operador (de la cima de P), hasta que encuentre un “(”.

     (b) Eliminar el “(” de P (no añadir a S).

[Fin de condicional]

6.- Si se encuentra un OPERANDO (2,23,6…), añadirlo a S.

[Fin del Bucle]

7.- Salir.

Nota: Los operadores siguen la siguiente jerarquía (El de arriba es el que tiene mayor jerarquía hasta abajo el que tiene la menor): 
^
*  /
+  -
)
(

--------librerias utilizadas:-----

import java.util.Scanner
import java.util.Stack

el codigo fue hecho en java a base de consola
tipo de ejecutable: Jar

