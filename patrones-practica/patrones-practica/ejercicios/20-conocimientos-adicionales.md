# Ejercicios — Conocimientos Adicionales (Búsqueda Binaria y Bits)

## Ejercicio 1
Completa `BusquedaBinariaRecursiva`, una versión recursiva (en vez de iterativa) de la
búsqueda binaria sobre un arreglo `int[]` ya ordenado.

```java
public class BusquedaBinariaRecursiva {

    public int buscar(int[] arreglo, int objetivo) {
        return buscarRec(arreglo, objetivo, 0, arreglo.length - 1);
    }

    private int buscarRec(int[] arreglo, int objetivo, int low, int high) {
        // Completar: caso base — si low > high, el elemento no está, devolver -1

        int mid = low + (high - low) / 2;

        if (arreglo[mid] == objetivo) {
            // Completar: devolver mid
        } else if (arreglo[mid] < objetivo) {
            // Completar: llamar recursivamente buscando en la mitad derecha
        } else {
            // Completar: llamar recursivamente buscando en la mitad izquierda
        }
    }
}
```

## Ejercicio 2
Completa `ConversorBinario`, que convierte un número decimal a su representación
binaria como `String`, usando el método de dividir por 2 y acumular los restos.

```java
public class ConversorBinario {

    public String decimalABinario(int numero) {
        if (numero == 0) {
            return "0";
        }

        StringBuilder binario = new StringBuilder();
        int n = numero;

        while (n > 0) {
            int resto = n % 2;
            // Completar: insertar el resto al INICIO de "binario"
            // (pista: binario.insert(0, resto))
            n = n / 2; // Completar: actualizar n dividiéndolo entre 2
        }

        return binario.toString();
    }
}
```

## Ejercicio 3
Completa `OperacionesBitwise`, que usa operadores bit a bit para resolver tareas
comunes sin usar operaciones aritméticas normales.

```java
public class OperacionesBitwise {

    public boolean esPar(int numero) {
        // Completar: usar el operador AND (&) contra 1; si da 0, es par
    }

    public int multiplicarPorDos(int numero) {
        // Completar: usar desplazamiento a la izquierda (<<) en 1 posición
    }

    public int dividirEntreDos(int numero) {
        // Completar: usar desplazamiento a la derecha (>>) en 1 posición
    }

    public boolean mismoSigno(int a, int b) {
        // Completar: usar XOR (^) entre a y b; si el resultado es >= 0,
        // ambos tienen el mismo signo
    }
}
```

## Ejercicio 4
Completa `ContadorBitsEncendidos`, que cuenta cuántos bits en `1` tiene la
representación binaria de un número, usando operaciones bit a bit (sin convertir a
String).

```java
public class ContadorBitsEncendidos {

    public int contarBits(int numero) {
        int contador = 0;
        int n = numero;

        while (n > 0) {
            // Completar: si el bit menos significativo de n es 1 (n & 1), incrementar contador
            n = n >> 1; // Completar: desplazar n una posición a la derecha
        }

        return contador;
    }
}
```

## Ejercicio 5
Completa `BuscadorDeRango`, que usa búsqueda binaria para encontrar la **primera**
posición de un arreglo ordenado donde el valor es mayor o igual a un umbral dado
(útil para búsquedas por rango).

```java
public class BuscadorDeRango {

    public int primeraPosicionMayorOIgual(int[] arreglo, int umbral) {
        int low = 0;
        int high = arreglo.length - 1;
        int resultado = -1;

        while (low <= high) {
            int mid = low + (high - low) / 2;

            if (arreglo[mid] >= umbral) {
                // Completar: este índice es un candidato válido, guardarlo en "resultado"
                // y seguir buscando más a la izquierda por si hay uno anterior (ajustar high)
            } else {
                // Completar: el valor es muy chico, buscar a la derecha (ajustar low)
            }
        }

        return resultado;
    }
}
```
