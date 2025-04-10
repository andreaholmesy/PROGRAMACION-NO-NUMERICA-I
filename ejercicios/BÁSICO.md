# 1. Tipos de Datos Básicos

```c
#include <stdio.h>
int main() {

    // 1. Enteros (int)
    int edad = 25;
    printf("Edad: %d\n", edad);  // %d para enteros
    // 2. Punto flotante (float)
    float altura = 1.75;
    printf("Altura: %.2f\n", altura);  // %.2f muestra 2 decimales
    // 3. Carácter (char)
    char inicial = 'A';
    printf("Inicial: %c\n", inicial);  // %c para caracteres
    // 4. Punto flotante de doble precisión (double)
    double pi = 3.1415926535;
    printf("Pi: %.4lf\n", pi);  // %.4lf para 4 decimales
    return 0;
}
```
# 2. Operadores Aritméticos
```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;

    // Suma
    printf("%d + %d = %d\n", a, b, a + b);

    // Resta
    printf("%d - %d = %d\n", a, b, a - b);

    // Multiplicación
    printf("%d * %d = %d\n", a, b, a * b);

    // División entera (cociente)
    printf("%d / %d = %d\n", a, b, a / b);

    // Módulo (residuo)
    printf("%d %% %d = %d\n", a, b, a % b);  // %% para imprimir %

    return 0;
}
```
# 4. Operadores Lógicos y Relacionales
```c
#include <stdio.h>

int main() {
    int a = 5, b = 10;

    // Operadores relacionales
    printf("%d < %d: %d\n", a, b, a < b);   // 1 (verdadero)
    printf("%d == %d: %d\n", a, b, a == b); // 0 (falso)

    // Operadores lógicos
    printf("!(%d == %d): %d\n", a, b, !(a == b)); // 1 (negación)
    printf("(%d > 0) && (%d < 20): %d\n", a, b, (a > 0) && (b < 20)); // 1 (AND)

    return 0;
}
```
# 5. Estructuras (struct)
```c
#include <stdio.h>

// Define una estructura
struct Persona {
    char nombre[50];
    int edad;
    float altura;
};

int main() {
    // Declara e inicializa una variable de tipo Persona
    struct Persona p1 = {"Juan", 30, 1.75};

    // Accede a los campos
    printf("Nombre: %s\n", p1.nombre);
    printf("Edad: %d\n", p1.edad);
    printf("Altura: %.2f\n", p1.altura);

    return 0;
}
```

# 6. Funciones y Argumentos
```c
#include <stdio.h>

// Declaración de la función
int sumar(int a, int b);

int main() {
    int num1 = 8, num2 = 7;
    int resultado = sumar(num1, num2);

    printf("%d + %d = %d\n", num1, num2, resultado);
    return 0;
}

// Definición de la función
int sumar(int a, int b) {
    return a + b;
}
```

