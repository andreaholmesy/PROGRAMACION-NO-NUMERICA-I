# 1. Introducción a C

El lenguaje C es conocido por su eficiencia, flexibilidad y acceso directo a la memoria, lo que lo hace ideal para programación de bajo y medio nivel.

¿Para qué se usa el lenguaje C?

C es un lenguaje multipropósito utilizado en una amplia variedad de aplicaciones, gracias a su equilibrio entre alto rendimiento y control sobre el hardware.

Sistemas operativos:
Fue creado para desarrollar UNIX, y hoy se usa en núcleos (kernels) de sistemas como Linux, Windows y macOS.
Ejemplo: El kernel de Linux está escrito en C en un 97% 

Drivers y firmware:
Controladores de dispositivos (impresoras, tarjetas gráficas) y firmware de hardware (ej.: BIOS de computadoras).

Desarrollo de lenguajes y herramientas:
Compiladores (como GCC), intérpretes (Python, PHP) y bases de datos (MySQL, SQLite) están escritos en C.


Programación de sistemas:
Creación de servidores, herramientas de red (como el protocolo TCP/IP), y sistemas de archivos.

El lenguaje C es el cimiento de la programación moderna. Aunque no es el más sencillo para principiantes, su dominio abre puertas a áreas como la robótica, sistemas operativos y desarrollo de hardware.

Tipos de Datos en C

Los tipos de datos definen el tipo de información que una variable puede almacenar y cómo se manipula en memoria. En C, son esenciales para optimizar el uso de recursos y garantizar operaciones correctas.

Se clasifican en: Tipos de Datos Primitivos, Tipos de Datos Derivados, Tipos de Datos Enumerados (enum).

1.Tipos de Datos Primitivos
Son los tipos básicos predefinidos por el lenguaje:

a)Enteros (int)
Almacenan números sin decimales.
Tamaño en memoria: 4 bytes (en sistemas de 32/64 bits).

Variantes:

•	short int (2 bytes)

•	long int (8 bytes)

•	unsigned int (4 bytes)

Ejemplo: int edad = 25;  

Qué es una variable  

Una variable es un contenedor en memoria que almacena datos (valores) durante la ejecución de un programa. Se llama variable porque su valor puede cambiar durante la ejecución. Es fundamental para manipular información dinámicamente en cualquier lenguaje, incluido C.

Características

Nombre (Identificador):

Es la etiqueta que usas para referirte a la variable (ej: edad, precio).


Reglas:

•	Puede contener letras, números y guiones bajos (_).
•	No puede empezar con un número.
•	No puede ser una palabra reservada (ej: int, if).


Ejemplos válidos: total, contador1, _dato.
Ejemplos inválidos: 1numero, float, mi-variable.

Tipo de dato:

Define qué tipo de información puede almacenar (entero, decimal, carácter, etc.).

Ejemplos: int, float, char, double.

Valor:
Es el dato concreto que guarda la variable. Puede modificarse múltiples veces.

b)Punto Flotante (float, double)
Almacenan números con decimales.

float:
Tamaño: 4 bytes.
Precisión: ~6-7 dígitos decimales.

double:
Tamaño: 8 bytes.
Precisión: ~15 dígitos decimales.

Ejemplo:
float precio = 19.99;  
double pi = 3.1415926535;  

c)Carácter (char)
Almacena un solo carácter (letra, símbolo o número).
Tamaño: 1 byte.

Ejemplo:
char letra = 'A';  

2.Tipos de Datos Derivados
Se construyen a partir de los primitivos:

a)Arreglos (Arrays)
Colección de elementos del mismo tipo.

Ejemplo:
int numeros[5] = {1, 2, 3, 4, 5};  

b)Punteros (*)
Almacenan direcciones de memoria de otras variables.

Ejemplo:
int x = 10;  
int *p = &x; 

c)Estructuras (struct)
Agrupan variables de distintos tipos bajo un nombre.

Ejemplo:

struct Alumno {  
  char nombre[50];  
  int edad;  
  float promedio;  
};  

3.Tipos de Datos Enumerados (enum)
Definen un conjunto de constantes enteras con nombres legibles.

Ejemplo:
enum DiaSemana {LUNES, MARTES, MIERCOLES, JUEVES, VIERNES};  

enum DiaSemana hoy = MARTES; // hoy vale 1 (por defecto

## Ejemplo de Uso de Tipos de Datos
```c
#include <stdio.h>  

int main() {  
    int entero = -42;  
    float decimal = 3.14;  
    char simbolo = '$';  
    unsigned short int edad = 30;  

    printf(Entero: %dn, entero);  
    printf(Decimal: %.2fn, decimal);  
    printf(Símbolo: %cn, simbolo);  
    printf(Edad: %hun, edad);  

    return 0;  
}  
```

