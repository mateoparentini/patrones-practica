# Ejercicios — Algoritmos de Ordenamiento

## Ejercicio 1
Completa `OrdenamientoBurbuja` (Bubble Sort) sobre una `List<Integer>`: en cada pasada,
comparar elementos adyacentes e intercambiarlos si están en el orden incorrecto.

```java
import java.util.List;

public class OrdenamientoBurbuja {

    public void ordenar(List<Integer> lista) {
        int n = lista.size();
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - 1 - i; j++) {
                if (lista.get(j) > lista.get(j + 1)) {
                    // Completar: intercambiar lista.get(j) y lista.get(j+1)
                    // usando una variable temporal y list.set(...)
                }
            }
        }
    }
}
```

## Ejercicio 2
Completa `OrdenamientoSeleccion` (Selection Sort) sobre un arreglo `int[]`: en cada
vuelta, buscar el menor elemento restante y colocarlo en su posición correcta.

```java
public class OrdenamientoSeleccion {

    public void ordenar(int[] arreglo) {
        int n = arreglo.length;
        for (int i = 0; i < n - 1; i++) {
            int indiceMinimo = i;
            for (int j = i + 1; j < n; j++) {
                if (arreglo[j] < arreglo[indiceMinimo]) {
                    // Completar: actualizar indiceMinimo
                }
            }
            // Completar: intercambiar arreglo[i] y arreglo[indiceMinimo]
        }
    }
}
```

## Ejercicio 3
Completa `OrdenamientoInsercion` (Insertion Sort) sobre una `List<Integer>`: tomar cada
elemento y desplazarlo hacia atrás hasta encontrar su posición correcta entre los ya
ordenados.

```java
import java.util.List;

public class OrdenamientoInsercion {

    public void ordenar(List<Integer> lista) {
        int n = lista.size();
        for (int i = 1; i < n; i++) {
            int clave = lista.get(i);
            int j = i - 1;

            while (j >= 0 && lista.get(j) > clave) {
                // Completar: mover lista.get(j) una posición a la derecha
                // (list.set(j+1, lista.get(j))) y decrementar j
            }

            // Completar: colocar "clave" en la posición j+1
        }
    }
}
```

## Ejercicio 4
Completa `BusquedaBinariaLista`, que implementa búsqueda binaria sobre una
`List<Integer>` ya ordenada, devolviendo el índice del elemento o `-1` si no existe.

```java
import java.util.List;

public class BusquedaBinariaLista {

    public int buscar(List<Integer> listaOrdenada, int objetivo) {
        int low = 0;
        int high = listaOrdenada.size() - 1;

        while (low <= high) {
            int mid = low + (high - low) / 2;

            if (listaOrdenada.get(mid) == objetivo) {
                // Completar: devolver mid
            } else if (listaOrdenada.get(mid) < objetivo) {
                // Completar: descartar la mitad izquierda (ajustar low)
            } else {
                // Completar: descartar la mitad derecha (ajustar high)
            }
        }

        return -1;
    }
}
```

## Ejercicio 5
Completa `OrdenamientoRapido` (Quicksort) sobre un arreglo `int[]`, usando el último
elemento del rango como pivote (misma idea que el ejemplo visto en clase, pero
completando vos la partición).

```java
public class OrdenamientoRapido {

    public void ordenar(int[] arreglo, int low, int high) {
        if (low < high) {
            int indicePivote = particionar(arreglo, low, high);
            ordenar(arreglo, low, indicePivote - 1);
            ordenar(arreglo, indicePivote + 1, high);
        }
    }

    private int particionar(int[] arreglo, int low, int high) {
        int pivote = arreglo[high];
        int i = low - 1;

        for (int j = low; j < high; j++) {
            if (arreglo[j] < pivote) {
                i++;
                // Completar: intercambiar arreglo[i] y arreglo[j]
            }
        }

        // Completar: intercambiar arreglo[i+1] y arreglo[high] (colocar el pivote en su lugar)
        // y devolver i + 1
    }
}
```
