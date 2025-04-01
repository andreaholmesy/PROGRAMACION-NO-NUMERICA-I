# Ejercicio 1:

Escribe un programa en C que sea una biblioteca y me permita almacenar 3 libros, utilizando arreglos y estructuras

## Resolución
```c
#include <stdio.h>  
struct Libro {
    char titulo[100];
    char autor[50];
    int anio_publicacion;
};

int main() {
    struct Libro biblioteca[3];
    
    // Ingresar datos para 3 libros
    for(int i = 0; i < 3; i++) {
        printf("\nLibro %d:\n", i+1);
        printf("Título: ");
        fgets(biblioteca[i].titulo, 100, stdin);
        
        printf("Autor: ");
        fgets(biblioteca[i].autor, 50, stdin);
        
        printf("Año de publicación: ");
        scanf("%d", &biblioteca[i].anio_publicacion);
        getchar(); // Limpiar el buffer
    }
    
    // Mostrar los libros
    printf("\n--- Biblioteca ---\n");
    for(int i = 0; i < 3; i++) {
        printf("\nLibro %d:\n", i+1);
        printf("Título: %s", biblioteca[i].titulo);
        printf("Autor: %s", biblioteca[i].autor);
        printf("Año: %d\n", biblioteca[i].anio_publicacion);
    }
    
    return 0;
}
```
