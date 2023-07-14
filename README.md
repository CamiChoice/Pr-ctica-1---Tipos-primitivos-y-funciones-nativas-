Práctica 1 - Conociendo los tipos primitivos y algunas operaciones y funciones nativas de Python 3
Autor: Claudio Morales D.
https://github.com/cmoralesd/conociendo-python
Otoño 2023


Para profundizar en conceptos y otros aspectos de programación con Python, recomiendo consultar el curso en línea e la Escuela de Ingenierías Industriales de la Universidad de Valencia, "Fundamentos de Programación en Python", disponible en este enlace: https://www2.eii.uva.es/fund_inf/python/index.html
1. Tipos primitivos: enteros, reales, booleanos, cadenas de texto y complejos
# Los tipos de variables para representar valores numéricos son int, float
var_1 = 1
var_2 = 1.
# Las variables booleanas pueden tener valor lógico True o False
var_3 = True
# Las cadenas de texto se definen utilizando comillas simples o dobles
var_4 = "texto 1"
var_5 = 'otro texto'
# En Jupyter Notebooks, es posible conocer rápidamente el valor contenido en una variable,
# simplemente observando la salida de consola (se muestra solo para la última operación de cada celda)
var_1
# Las operaciones de comparación entregan como resultado True o False
var_1 > var_2
# Para conocer el tipo de variable se utiliza type()
type(var_5)
# Los números complejos pueden representarse por una variable de tipo complex,
# se escribe en forma rectangular (a + bj), agregando el operador j
var_6 = 3 + 2j
var_6
# Es posible definir varias variables simultáneamente, en una única línea, separando por comas
radio, altura, PI = 2.1, 1.5, 3.14159

# también se puede asignar el resultado de una operación a una variable
volumen_cilindro = 2*PI*radio*altura
volumen_cilindro
2. Operaciones y funciones nativas con variables de tipos primitivos
# La función abs() calcula el valor absoluto o módulo de variables numéricas
num1, num2, num3 = 7.5, -3.2, 2 + 3.2j
abs(num3)
# El cálculo de potencias se realiza con el operador **
3**2
# Es posible calcular potencias con exponentes racionales
2**(1/2)
# Incluso se pueden realizar cálculos cuyo resultado se extiende al campo de los números complejos
(-2)**(1/2)
# CUIDADO! Siempre es importante tener en cuenta las prioridades en los cálculos matemáticos 
# Estos 5 cálculos entregan resultados distintos
# ¿Cuál de ellos corresponde a 2 veces la raíz cuadrada de -3?

valor_1 = 2*-3**1/2 
valor_2 = 2*(-3)**1/2 
valor_3 = 2*(-3)**(1/2)
valor_4 = (2*-3)**(1/2)
valor_5 = 2*(-3**1/2)
# Para las variables de tipo float, es posible redondear decimales con round()
round(2**(1/2), 3)
# Cada variable es, estrictamente hablando, una instancia de una clase y tiene todas
# las atributos y métodos que han sido definidos para esa clase.
# Para conocerlos, se puede utilizar la función dir()
my_var = 3.2
dir(my_var)
my_var.is_integer()
# Para las variables de tipo str, hay varios métodos que es bueno conocer
texto = "un texto de ejemplo"
dir(texto)
# En Jupyter Notebooks, los parámetros y métodos disponibles se pueden identificar
# fácilmente mediante autocompletar (tecla TAB)
text_value = "132"
# Un método muy utilizado al trabajar con cadenas de texto es .split(), que sirve para
#  separar sectores de una cadena en una lista. Se utiliza indicando el caracter de separación.
datos_recibidos = '12.5, 3.25, 44,3, 120, 0'
datos_recibidos.split(',')
# Dado que trabajaremos frecuentemente con valores numéricos y cadenas de texto,
# conviene conocer las funciones de conversión más comunes:
text_value = "1.32"
float(text_value)
# También es posible transformar números a cadenas de texto
value = round(2**(1/2), 4)
str(value)
3. La función print()
# Las cadenas de texto pueden enviarse a la consola en tiempo de ejecución usando la función print()
msg = 'mensaje a la consola...'
print(msg)
# Las cadenas de texto pueden concatenarse, con el operador +
txt1 = 'El mensaje comienza aquí'
txt2 =  'y concluye aquí.'
print(txt1 + txt2)
# Si se envían variables numéricas a una función print(), son convertidas a str y enviadas a consola
value = 3.14
print(value)
# Varias variables y cadenas de texto pueden enviarse a print(), separadas por comas:
texto = 'valor:'
value = 3.14
print ("la variable tiene", texto, value)
# Pero una forma más adecuada de dar formato al texto es mediante el método .format()
valnum = 1
value = 3.14
print('El valor de la variable {} es: {}'.format(valnum, value))
# Que puede también escribirse en una forma más cómoda
print(f'El valor de la variable {valnum} es: {value}')
ACTIVIDAD
Se tienen variables de texto que contienen datos sobre las dimensiones de una caja de encomienda. Con esta información se calcula el costo de envío por volumen, a razón de $15990 por metro cúbico, al cual se le suma un costo fijo de $2500.

A partir de las definiciones de variables dadas, escriba un código que:

Transforme los valores numéricos almacenados en text_dato_1 , text_dato_2 y text_dato_3 en variables de tipo float. Asigne los resultados a las variables largo, ancho y largo, respectivamente.
Con los valores numéricos de largo, ancho y largo, calcule el volumen de la caja como volumen = largo * ancho * alto
Imprima un mensaje en pantalla que diga, por ejemplo: "El volumen de la caja es 0.32 m3". El número debe estar redondeado a dos decimales.
Calcule el costo de envío como el producto del volumen calculado por $15990, más el costo fijo de $2500. El resultado debe quedar almacenado en una variable llamada costo_envio, que debe ser de tipo int.
Imprima un mensaje en pantalla que exprese el costo de envío (almacenado en la variable costo_envio) y el detalle de costo por volumen y costo fijo, por ejemplo: "El costo de envío es $8017, compuesto por un costo por volumen de $5517 más $2500 por servicio".
# datos de entrada
text_dato_1 = '0.5'    # largo de la caja
text_dato_2 = '0.85'   # ancho de la caja
text_dato_3 = '0.25'   # alto de la caja

# Escriba su código aquí ---->
# transformamos los valores recibidos a tipo 'float'
largo = float(text_dato_1)
ancho = float(text_dato_2)
alto = float(text_dato_3)

# calculamos volumen
volumen = largo * ancho * alto

# imprimimos un mensaje en pantalla
print(f'El volumen de la caja es {round(volumen, 2)} m3')

# calculamos costo de envío
costo_volumen = int(volumen * 15990)
costo_envio = costo_volumen + 2500

# imprimimos mensaje final
print(f'El costo de envío es ${costo_envio}, compuesto por un costo por volumen de ${costo_volumen} más $2500 por servicio')
El volumen de la caja es 0.11 m3
El costo de envío es $4198, compuesto por un costo por volumen de $1698 más $2500 por servicio
# Si su código funciona correctamente, el siguiente código debiera ejecutarse sin errores:
# *** NO MODIFIQUE ESTA CELDA ***

print(f'El valor almacenado en la variable costo_envio es $ {costo_envio}')
print(f'La variable costo_envio es de tipo {type(costo_envio)}')
El valor almacenado en la variable costo_envio es $ 4198
La variable costo_envio es de tipo <class 'int'>
