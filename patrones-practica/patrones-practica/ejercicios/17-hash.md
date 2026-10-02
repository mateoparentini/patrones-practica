# Ejercicios — Tablas Hash (HashMap)

## Ejercicio 1
Completa `ContadorPalabras`, que usa un `Map<String, Integer>` para contar cuántas
veces aparece cada palabra en un texto.

```java
import java.util.HashMap;
import java.util.Map;

public class ContadorPalabras {
    private Map<String, Integer> conteo = new HashMap<>();

    public void procesarTexto(String texto) {
        String[] palabras = texto.toLowerCase().split(" ");
        for (String palabra : palabras) {
            // Completar: si la palabra ya está en el mapa, incrementar su contador en 1;
            // si no está, agregarla con valor 1
        }
    }

    public int vecesQueAparece(String palabra) {
        // Completar: devolver 0 si la palabra no está en el mapa
    }
}
```

## Ejercicio 2
Completa `DetectorDuplicados`, que usa un `Set<Integer>` (basado en hash) para detectar
si un arreglo tiene números repetidos.

```java
import java.util.HashSet;
import java.util.Set;

public class DetectorDuplicados {

    public boolean tieneDuplicados(int[] numeros) {
        Set<Integer> vistos = new HashSet<>();

        for (int numero : numeros) {
            // Completar: si "numero" ya está en "vistos", devolver true;
            // si no, agregarlo al set
        }

        return false;
    }
}
```

## Ejercicio 3
Completa `AgrupadorAnagramas`, que usa un `Map<String, List<String>>` para agrupar
palabras que son anagramas entre sí (misma clave: sus letras ordenadas).

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class AgrupadorAnagramas {
    private Map<String, List<String>> grupos = new HashMap<>();

    public void agregarPalabra(String palabra) {
        char[] letras = palabra.toCharArray();
        Arrays.sort(letras);
        String clave = new String(letras);

        // Completar: si "clave" no existe todavía en "grupos", crear una lista vacía
        // y asociarla a esa clave; luego, en cualquier caso, agregar "palabra" a esa lista
    }

    public List<String> obtenerGrupo(String palabra) {
        char[] letras = palabra.toCharArray();
        Arrays.sort(letras);
        String clave = new String(letras);
        // Completar: devolver la lista asociada a esa clave, o una lista vacía si no existe
    }
}
```

## Ejercicio 4
Completa `CacheResultados`, que usa un `Map<Integer, Long>` para memoizar (cachear) el
resultado de una operación costosa (simulada), evitando recalcular si ya se pidió ese
valor antes.

```java
import java.util.HashMap;
import java.util.Map;

public class CacheResultados {
    private Map<Integer, Long> cache = new HashMap<>();

    public long calcularCuadradoCostoso(int n) {
        // Completar: si "n" ya está en cache, devolver el valor cacheado sin recalcular
        // si no está, calcular (long) n * n, guardarlo en cache y devolverlo
    }
}
```

## Ejercicio 5
Completa `IndiceInventario`, que usa un `Map<String, Integer>` para mapear nombre de
producto a stock, con el método adicional `transferir` que mueve unidades de un
producto a otro (ambos deben existir).

```java
import java.util.HashMap;
import java.util.Map;

public class IndiceInventario {
    private Map<String, Integer> stock = new HashMap<>();

    public void agregarProducto(String nombre, int cantidad) {
        // Completar
    }

    public boolean transferir(String origen, String destino, int cantidad) {
        // Completar: si alguno de los dos productos no existe en el mapa, devolver false;
        // si el origen no tiene suficiente stock, devolver false;
        // si todo es válido, restar "cantidad" del origen, sumarla al destino y devolver true
    }
}
```
