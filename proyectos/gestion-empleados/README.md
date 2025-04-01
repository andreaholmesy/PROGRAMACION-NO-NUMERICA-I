# Desarrolle un sistema de gestion de empleados en C
## Solución

```c
#include <stdio.h>
#include <string.h>

#define MAX_EMPLEADOS 10

struct Fecha {
    int dia, mes, anio;
};

struct Empleado {
    char nombre[50];
    char puesto[30];
    float salario;
    struct Fecha fecha_contratacion;
};

void agregarEmpleado(struct Empleado empleados[], int *numEmpleados) {
    if(*numEmpleados >= MAX_EMPLEADOS) {
        printf("No se pueden agregar más empleados.\n");
        return;
    }
    
    struct Empleado nuevo;
    
    printf("\nNuevo empleado:\n");
    printf("Nombre: ");
    fgets(nuevo.nombre, 50, stdin);
    nuevo.nombre[strcspn(nuevo.nombre, "\n")] = 0; // Eliminar el salto de línea
    
    printf("Puesto: ");
    fgets(nuevo.puesto, 30, stdin);
    nuevo.puesto[strcspn(nuevo.puesto, "\n")] = 0;
    
    printf("Salario: ");
    scanf("%f", &nuevo.salario);
    
    printf("Fecha de contratación (dd mm aaaa): ");
    scanf("%d %d %d", &nuevo.fecha_contratacion.dia,
                      &nuevo.fecha_contratacion.mes,
                      &nuevo.fecha_contratacion.anio);
    getchar(); // Limpiar el buffer
    
    empleados[*numEmpleados] = nuevo;
    (*numEmpleados)++;
    
    printf("Empleado agregado con éxito!\n");
}

void listarEmpleados(struct Empleado empleados[], int numEmpleados) {
    printf("\n--- Lista de Empleados ---\n");
    for(int i = 0; i < numEmpleados; i++) {
        printf("\nEmpleado %d:\n", i+1);
        printf("Nombre: %s\n", empleados[i].nombre);
        printf("Puesto: %s\n", empleados[i].puesto);
        printf("Salario: %.2f\n", empleados[i].salario);
        printf("Fecha contratación: %d/%d/%d\n", 
               empleados[i].fecha_contratacion.dia,
               empleados[i].fecha_contratacion.mes,
               empleados[i].fecha_contratacion.anio);
    }
}

int main() {
    struct Empleado empleados[MAX_EMPLEADOS];
    int numEmpleados = 0;
    int opcion;
    
    do {
        printf("\nSistema de Gestión de Empleados\n");
        printf("1. Agregar empleado\n");
        printf("2. Listar empleados\n");
        printf("3. Salir\n");
        printf("Seleccione una opción: ");
        scanf("%d", &opcion);
        getchar(); // Limpiar el buffer
        
        switch(opcion) {
            case 1:
                agregarEmpleado(empleados, &numEmpleados);
                break;
            case 2:
                listarEmpleados(empleados, numEmpleados);
                break;
            case 3:
                printf("Saliendo del sistema...\n");
                break;
            default:
                printf("Opción no válida.\n");
        }
    } while(opcion != 3);
    
    return 0;
}
```
