# Paradigmas-de-programaci-n---Gestor-de-citas-de-hospital
Equipo  - 3CV4
Pruebas de validación y robustez
Se realizaron diez pruebas utilizando entradas incorrectas o inesperadas, con el objetivo de comprobar que el programa pudiera manejar errores cometidos por el usuario sin finalizar inesperadamente.
Prueba 1. Entrada de texto en las horas:
El usuario introduce abc en el campo de horas y 1000 como monto. En la primera versión del programa se producía un error porque abc no podía convertirse a número. Después de modificar el programa, se muestra un mensaje de error y se solicita nuevamente el dato.
Prueba 2. Entrada de texto en el monto:
El usuario introduce 50 horas y escribe mil como monto. La primera versión producía un error al intentar convertir mil a número. Con la validación implementada, el programa informa que debe introducirse solamente un número y vuelve a solicitar el monto.
Prueba 3. Campo de horas vacío:
El usuario deja vacío el campo de horas e introduce 1000 como monto. Originalmente se producía un error de conversión. Después de la corrección, el sistema detecta que el campo está vacío y solicita nuevamente las horas.
Prueba 4. Campo de monto vacío:
El usuario introduce 50 horas y deja vacío el campo del monto. El programa corregido detecta que el campo no contiene información, muestra un mensaje de error y vuelve a solicitar el monto.
Prueba 5. Uso de coma decimal:
El usuario introduce 50,5 como cantidad de horas y 1000 como monto. La primera versión no reconocía correctamente la entrada con coma decimal y producía un error. El programa de validación detecta que la entrada no tiene el formato numérico esperado y solicita nuevamente el dato.
Prueba 6. Uso de separador de miles:
El usuario introduce 50 horas y 1,000 como monto. La primera versión no podía convertir correctamente este formato a un número. El programa corregido rechaza la entrada y solicita que se introduzca solamente un valor numérico válido.
Prueba 7. Uso del símbolo de moneda:
El usuario introduce 50 horas y $1000 como monto. La primera versión producía un error porque el símbolo $ forma parte de la cadena de entrada. La versión corregida muestra un mensaje indicando que solamente debe introducirse un número.
Prueba 8. Introducción de NaN:
El usuario introduce NaN como cantidad de horas y 1000 como monto. La primera versión no generaba un error, pero podía producir un resultado incorrecto, ya que NaN no se comporta como un número normal en las comparaciones. La versión corregida verifica que los valores sean números finitos y rechaza NaN.
Prueba 9. Introducción de infinito:
El usuario introduce inf como cantidad de horas y 1000 como monto. La primera versión podía interpretar el valor como infinito y asignar una devolución del 100 %. Esto representa un resultado incorrecto. La versión corregida utiliza una validación de números finitos y rechaza este tipo de entrada.
Prueba 10. Texto acompañado de unidades:
El usuario introduce 50.5 horas y 1000 pesos como monto. La primera versión no podía convertir 1000 pesos a un número y terminaba con un error. La versión corregida informa al usuario que debe introducir solamente el valor numérico.
Resultado de las pruebas
Las pruebas permitieron identificar que el programa original funcionaba correctamente con entradas numéricas válidas, pero podía fallar ante entradas incorrectas realizadas por el usuario. Para solucionar estos problemas se incorporó una validación de entrada que utiliza ciclos while, conversión a float y math.isfinite().
De esta manera, cuando el usuario introduce un dato incorrecto, el programa no termina, sino que muestra un mensaje indicando el problema y solicita nuevamente la información. Esto hace que el sistema sea más robusto frente a errores de captura.
