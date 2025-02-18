Algoritmo Calculadora
    // Definir arreglos para almacenar números y operaciones
    Definir numeros Como Real[10]
    Definir operaciones Como Caracter[10]
    Definir cantidadNumeros, cantidadOperaciones Como Entero
    Definir resultado Como Real
    
    // Solicitar al usuario la cantidad de números a operar
    Escribir "Ingrese la cantidad de números a operar (máximo 10):"
    Leer cantidadNumeros
    
    // Validar que la cantidad de números sea válida
    Si cantidadNumeros < 2 O cantidadNumeros > 10 Entonces
        Escribir "La cantidad de números debe ser entre 2 y 10."
        FinAlgoritmo
    FinSi
    
    // Solicitar al usuario que ingrese los números
    Para i <- 0 Hasta cantidadNumeros - 1 Hacer
        Escribir "Ingrese el número ", i + 1, ":"
        Leer numeros[i]
    FinPara
    
    // Solicitar al usuario la cantidad de operaciones a realizar
    Escribir "Ingrese la cantidad de operaciones a realizar (máximo ", cantidadNumeros - 1, "):"
    Leer cantidadOperaciones
    
    // Validar que la cantidad de operaciones sea válida
    Si cantidadOperaciones < 1 O cantidadOperaciones >= cantidadNumeros Entonces
        Escribir "La cantidad de operaciones debe ser al menos 1 y menor que la cantidad de números."
        FinAlgoritmo
    FinSi
    
    // Solicitar al usuario que ingrese las operaciones
    Para i <- 0 Hasta cantidadOperaciones - 1 Hacer
        Escribir "Ingrese la operación ", i + 1, " (+, -, *, /):"
        Leer operaciones[i]
    FinPara
    
    // Inicializar el resultado con el primer número
    resultado <- numeros[0]
    
    // Realizar las operaciones
    Para i <- 0 Hasta cantidadOperaciones - 1 Hacer
        Segun operaciones[i] Hacer
            Caso '+':
                resultado <- resultado + numeros[i + 1]
            Caso '-':
                resultado <- resultado - numeros[i + 1]
            Caso '*':
                resultado <- resultado * numeros[i + 1]
            Caso '/':
                Si numeros[i + 1] = 0 Entonces
                    Escribir "Error: División por cero."
                    FinAlgoritmo
                FinSi
                resultado <- resultado / numeros[i + 1]
            De Otro Modo:
                Escribir "Operación no válida."
                FinAlgoritmo
        FinSegun
    FinPara
    
    // Mostrar el resultado final
    Escribir "El resultado de las operaciones es: ", resultado
    
FinAlgoritmo
