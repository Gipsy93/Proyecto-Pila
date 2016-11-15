
------Primeros pasos para conversi�n notaci�n Infija a Postfija.

La notaci�n Postfija es un m�todo algebraico alternativo de introducci�n de datos que permite reducir el acceso a la memoria del ordenador, sobretodo en calculos masivos y complejos ya que los c�lculos se realizan secuencialmente seg�n se van introduciendo los operadores (en vez de tener que esperar a escribir la expresi�n al completo).
Basicamente consiste en que en una expresi�n de ese tipo primero est�n los operandos y despu�s viene el operador. 

Ej:
         "3+5" pasado a notaci�n Postfija seria: "3 5 +" 


------Pasos para la conversi�n Infijo a Postfijo usando pilas.  

     EXPR = Expresi�n aritm�tica notaci�n infija ( Ej: 2*(23+6)-1 )
     E = pila de entrada
     P = pila temporal para los operadores
     S = pila de salida  

1.- A�adir �(� al principio y �)� al final de EXPR. Seguidamente agregar uno a uno todos los parametros de EXPR a la Pila E.
(,2,*,(,23,+,6,),-,1,)

2.- Examinar E de izquierda a derecha y repetir los pasos 3 a 6 para cada elemento de E hasta que esta quede vac�a.

3.- Si se encuentra �(�, meterlo en P.

4.- Si se encuentra un OPERADOR (+,-,*,/,^) entonces:

     (a) Repetidamente sacar de P y a�adir a S cada operador (de la cima de P) que tenga la misma precedencia o mayor que el operador de E.

     (b) A�adir OPERADOR a P.

[Fin de condicional]

5.- Si se encuentra un �)�, entonces:

     (a) Repetidamente sacar de P y a�adir a S cada operador (de la cima de P), hasta que encuentre un �(�.

     (b) Eliminar el �(� de P (no a�adir a S).

[Fin de condicional]

6.- Si se encuentra un OPERANDO (2,23,6�), a�adirlo a S.

[Fin del Bucle]

7.- Salir.

Nota: Los operadores siguen la siguiente jerarqu�a (El de arriba es el que tiene mayor jerarqu�a hasta abajo el que tiene la menor): 
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

