# 🚀 Guía de Estudio: Programación en C  
Ejercicios prácticos para dominar conceptos básicos de C.  

---

## 📚 Temas Cubiertos  
1. Tipos de Datos Básicos  
2. Operadores Aritméticos  
3. Incremento y Decremento  
4. Operadores Lógicos y Relacionales  
5. Estructuras (`struct`)  
6. Funciones y Argumentos  

---

# 1. Tipos de Datos Básicos
Teoría:

int: Almacena números enteros (ej: -5, 0, 100).
Rango típico: -32,768 a 32,767 (para 16 bits).
float: Números decimales de precisión simple (ej: 3.14f).
Sufijo f para diferenciarlo de double.
char: Almacena un carácter (ej: 'a', '$').
Internamente, se guarda como un entero (ASCII).
double: Decimales de doble precisión (ej: 3.1415926535).

## Ejemplos:

```c
int poblacion = 8000000;
float temperatura = -5.5f;
char simbolo = '#';
double distancia_estrella = 9.4607e15; // Notación científica

```
## Errores Comunes:

Usar %d para imprimir float (debe ser %f).

Olvidar las comillas simples en char: char c = "A"; → Error.

## Ejercicios:

Declara una variable precio de tipo double e inicialízala con 99.95.

¿Qué imprime este código?
```c
char letra = 66;
printf("%c", letra); 
```
# 2. Operadores Aritméticos
Teoría:
+ (Suma), - (Resta), * (Multiplicación), / (División), % (Módulo).
Precedencia de operadores: Paréntesis → Multiplicación/División → Suma/Resta.
División entera vs. decimal:

```c
int a = 10 / 3;   // 3 (división entera)
float b = 10 / 3; // 3.000000 (pero cuidado, 10 y 3 son enteros).
float c = 10.0 / 3; // 3.333333 (correcto).
```

## Ejemplo:
```c
int x = 5, y = 2;
int suma = x + y;       // 7
int modulo = x % y;     // 1
float division = x / y; // 2.0 (¿Por qué no 2.5?)
```
## Ejercicios:

1.- Calcula: (3 + 5 * 2) % 4.
2.- ¿Cómo obtener el resultado decimal de 7 / 2?

# 3. Operadores de Incremento y Decremento
Teoría:

Pre-incremento (++x): Incrementa primero, luego usa el valor.
Post-incremento (x++): Usa el valor, luego incrementa.
Aritmética en asignaciones: x += 5; es equivalente a x = x + 5;.

## Ejemplos:
```c
int a = 5;
int b = ++a; // a = 6, b = 6
int c = a++; // c = 6, a = 7
```
```c
int x = 3;
int y = x++ + --x; 
// Paso a paso: 
// 1. x++ → y usa 3, luego x = 4.
// 2. --x → x = 3, luego suma: 3 + 3 = 6.
// Resultado: y = 6.
```
## Ejercicios:
¿Qué valor final tiene x?

```c
int x = 4;
x += x++ * --x;
```
# Operadores Lógicos y Relacionales
Teoría:

Relacionales: Comparan valores (==, !=, <, >, <=, >=).
Lógicos: Combinan condiciones (&&, ||, !).
Resultado booleano: 1 (verdadero) o 0 (falso).
Tabla de Verdad para && y ||:

A	 B 	A && B	 A || B
0	 0	  0	       0
0  1	  0	       1
1	 0	  0	       1
1	 1	  1	       1

## Ejemplo:
```c
int edad = 18;
float promedio = 4.5;
int beca = (edad >= 18) && (promedio >= 4.0); // beca = 1 (verdadero)
```
## Ejercicios:

1.- Evalúa: !(5 > 3) || (2 == 3).
2.- ¿Cómo verificar si un número está entre 10 y 20?

# 5. Estructuras (struct)
Teoría:

Agrupan variables de diferentes tipos bajo un mismo nombre.
Sintaxis: 
```c
struct Nombre {
    tipo campo1;
    tipo campo2;
};
```
Inicialización:
```c
struct Nombre var = {valor1, valor2};
```
## Ejemplo Completo:
```c
struct Fecha {
    int dia;
    char mes[10];
    int año;
};

int main() {
    struct Fecha hoy = {25, "Diciembre", 2023};
    printf("Hoy es %d de %s de %d", hoy.dia, hoy.mes, hoy.año);
    return 0;
}
```
## Ejercicios:

1.- Crea una estructura Producto con nombre, precio y cantidad.
2.- Escribe una función que calcule el costo total de un producto (precio * cantidad).

# 6. Funciones y Argumentos
Teoría:

Declaración: tipo nombre(tipo param1, tipo param2);
Definición: Implementación de la función.
Parámetros por valor: Las funciones reciben copias de los valores.

## Ejemplo con Parámetros:
```c
int potencia(int base, int exponente) {
    int resultado = 1;
    for (int i = 0; i < exponente; i++) {
        resultado *= base;
    }
    return resultado;
}

int main() {
    printf("%d", potencia(2, 3)); // Imprime 8
    return 0;
}
```

## Errores Comunes:

Olvidar el return en funciones no void.
Usar parámetros incorrectos: potencia(2.5, 3) → Error de tipo.

## Ejercicios:

Escribe una función esPositivo(int n) que retorne 1 si n > 0.
¿Qué imprime este código?
```c
void cambiar(int a) {
    a = 10;
}
int main() {
    int x = 5;
    cambiar(x);
    printf("%d", x); // Respuesta: 5 (los parámetros se pasan por valor).
    return 0;
}
```

# Ejercicios Integrados (Nivel Examen)
## 1. Problema de Estructuras y Funciones:
Crea una estructura Circulo con radio y coordenadas (x, y).
Escribe una función areaCirculo que calcule el área (π * radio²).
Escribe otra función estaDentro que determine si un punto (a, b) está dentro del círculo.

Solución:
```c
#include <stdio.h>
#include <math.h>

struct Circulo {
    float radio;
    float x;
    float y;
};

float areaCirculo(struct Circulo c) {
    return 3.1416 * c.radio * c.radio;
}

int estaDentro(struct Circulo c, float a, float b) {
    float distancia = sqrt(pow(a - c.x, 2) + pow(b - c.y, 2));
    return (distancia <= c.radio) ? 1 : 0;
}
```


## 2. Operadores Lógicos y Aritméticos:
 
Si a = 5, b = 3, y c = 7, evalúa:
(a % b == 2) && !(c < (a + b)) || (a * b > 20)

Solución:
(5 % 3 == 2) → 2 == 2 → 1.
!(7 < 8) → !1 → 0.
(15 > 20) → 0.
Resultado final: 1 && 0 || 0 → 0.
