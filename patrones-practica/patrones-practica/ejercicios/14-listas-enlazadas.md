# Ejercicios — Listas Enlazadas (LinkedList)

## Ejercicio 1
Completa `ListaPersonalizada` para administrar nombres, usando un `ArrayList<String>`
interno, validando los índices.

```java
import java.util.ArrayList;

public class ListaPersonalizada {
    private ArrayList<String> lista = new ArrayList<>();

    public void agregarAlInicio(String nombre) {
        // Completar
    }

    public void agregarAlFinal(String nombre) {
        // Completar
    }

    public void eliminarPorIndice(int index) {
        // Completar: validar índice (0 a size()-1), lanzar
        // IndexOutOfBoundsException("Índice fuera de rango") si es inválido
    }

    public String obtener(int index) {
        // Completar: validar índice y devolver el elemento
    }
}
```

## Ejercicio 2
Completa `HistorialNavegacion` usando `LinkedList<String>`, que permita moverse
hacia atrás y hacia adelante como el historial de un navegador.

```java
import java.util.LinkedList;

public class HistorialNavegacion {
    private LinkedList<String> historial = new LinkedList<>();

    public void visitar(String url) {
        // Completar: agregar la url al final del historial
    }

    public String paginaAnterior() {
        // Completar: eliminar y devolver la última url visitada (removeLast),
        // o null si el historial está vacío
    }

    public String primeraPagina() {
        // Completar: devolver (sin eliminar) la primera url del historial,
        // o null si está vacío
    }
}
```

## Ejercicio 3
Completa `ListaDeTareas` usando `LinkedList<String>`, con prioridad: las tareas
urgentes se agregan al inicio, las normales al final.

```java
import java.util.LinkedList;

public class ListaDeTareas {
    private LinkedList<String> tareas = new LinkedList<>();

    public void agregarUrgente(String tarea) {
        // Completar
    }

    public void agregarNormal(String tarea) {
        // Completar
    }

    public String completarSiguiente() {
        // Completar: elimina y devuelve la primera tarea de la lista,
        // o null si no hay tareas
    }

    public int cantidadPendientes() {
        // Completar
    }
}
```

## Ejercicio 4
Completa `ListaInvertible`, que permite agregar enteros y devolver la lista invertida
sin modificar la original.

```java
import java.util.ArrayList;
import java.util.List;

public class ListaInvertible {
    private List<Integer> numeros = new ArrayList<>();

    public void agregar(int numero) {
        // Completar
    }

    public List<Integer> obtenerInvertida() {
        // Completar: crear y devolver una nueva lista con los elementos en orden inverso,
        // sin modificar "numeros"
    }
}
```

## Ejercicio 5
Completa `ListaSinDuplicados`, que solo agrega un elemento si todavía no está presente.

```java
import java.util.ArrayList;
import java.util.List;

public class ListaSinDuplicados {
    private List<String> elementos = new ArrayList<>();

    public boolean agregar(String elemento) {
        // Completar: si "elemento" ya está en la lista (contains), no agregarlo y
        // devolver false; si no está, agregarlo y devolver true
    }

    public List<String> obtenerTodos() {
        // Completar
    }
}
```
