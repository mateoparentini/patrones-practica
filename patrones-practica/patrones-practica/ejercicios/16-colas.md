# Ejercicios — Colas (Queue)

## Ejercicio 1
Completa `FilaAtencion`, que usa una `Queue<String>` (con `LinkedList`) para atender
clientes en orden de llegada.

```java
import java.util.LinkedList;
import java.util.Queue;

public class FilaAtencion {
    private Queue<String> fila = new LinkedList<>();

    public void llegarCliente(String nombre) {
        // Completar: usar offer()
    }

    public String atenderSiguiente() {
        // Completar: usar poll(); si la fila está vacía poll() ya devuelve null
    }

    public int cantidadEnEspera() {
        // Completar
    }
}
```

## Ejercicio 2
Completa `PlanificadorRoundRobin`, que reparte turnos de CPU entre procesos usando una
`Queue<String>`: cada vez que se atiende un proceso, se lo vuelve a poner al final de la cola.

```java
import java.util.LinkedList;
import java.util.Queue;

public class PlanificadorRoundRobin {
    private Queue<String> procesos = new LinkedList<>();

    public void agregarProceso(String nombre) {
        // Completar
    }

    public String ejecutarSiguienteTurno() {
        // Completar: sacar el proceso del frente (poll), volver a agregarlo
        // al final (offer) y devolver su nombre; si la cola está vacía, devolver null
    }
}
```

## Ejercicio 3
Completa `VerificadorPalindromo`, que usa una `Queue<Character>` y una `Stack<Character>`
en paralelo para comprobar si una palabra es un palíndromo.

```java
import java.util.LinkedList;
import java.util.Queue;
import java.util.Stack;

public class VerificadorPalindromo {

    public boolean esPalindromo(String palabra) {
        Queue<Character> cola = new LinkedList<>();
        Stack<Character> pila = new Stack<>();

        for (char c : palabra.toCharArray()) {
            // Completar: agregar el carácter tanto a la cola (offer) como a la pila (push)
        }

        while (!cola.isEmpty()) {
            // Completar: comparar el frente de la cola (poll) contra el tope de la pila (pop);
            // si en algún momento son distintos, devolver false
        }

        return true;
    }
}
```

## Ejercicio 4
Completa `ColaImpresion`, que administra trabajos de impresión con prioridad usando
`PriorityQueue<Integer>` (menor número = mayor prioridad).

```java
import java.util.PriorityQueue;

public class ColaImpresion {
    private PriorityQueue<Integer> trabajos = new PriorityQueue<>();

    public void agregarTrabajo(int prioridad) {
        // Completar: usar offer()
    }

    public Integer imprimirSiguiente() {
        // Completar: usar poll()
    }

    public boolean hayTrabajosPendientes() {
        // Completar: usar isEmpty()
    }
}
```

## Ejercicio 5
Completa `SimuladorBuffer`, una cola con capacidad máxima: si está llena, no se puede
agregar más y debe informarlo.

```java
import java.util.LinkedList;
import java.util.Queue;

public class SimuladorBuffer {
    private Queue<String> buffer = new LinkedList<>();
    private int capacidadMaxima;

    public SimuladorBuffer(int capacidadMaxima) {
        this.capacidadMaxima = capacidadMaxima;
    }

    public boolean agregarDato(String dato) {
        // Completar: si buffer.size() ya alcanzó la capacidad máxima, devolver false
        // sin agregar; si hay espacio, agregar (offer) y devolver true
    }

    public String procesarDato() {
        // Completar: usar poll()
    }
}
```
