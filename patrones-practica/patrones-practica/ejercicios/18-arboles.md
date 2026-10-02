# Ejercicios — Árboles Binarios y Recorridos (7 ejercicios — tema a reforzar)

## Ejercicio 1
Completa `ArbolEnteros` para insertar valores siguiendo las reglas de un árbol binario
de búsqueda (menor a la izquierda, mayor a la derecha, sin duplicados) y recorrerlo
en **inorden** (izquierda, nodo, derecha).

```java
class NodoEntero {
    int valor;
    NodoEntero izquierdo;
    NodoEntero derecho;

    public NodoEntero(int valor) {
        this.valor = valor;
    }
}

public class ArbolEnteros {
    private NodoEntero raiz;

    public void insertar(int valor) {
        // Completar: actualizar raiz usando insertarRec(raiz, valor)
    }

    private NodoEntero insertarRec(NodoEntero nodo, int valor) {
        // Completar: caso base (nodo null), y recursión por izquierda/derecha según
        // corresponda; si el valor ya existe, no insertar nada
    }

    public void inOrden() {
        // Completar: llamar al método auxiliar recursivo desde la raíz
    }

    private void inOrdenRec(NodoEntero nodo) {
        // Completar: izquierda, imprimir valor, derecha
    }
}
```

## Ejercicio 2
Completa `ArbolEnteros` (continuación) con el recorrido en **postorden**
(izquierda, derecha, nodo) y el cálculo de la **altura** del árbol.

```java
class NodoEntero2 {
    int valor;
    NodoEntero2 izquierdo;
    NodoEntero2 derecho;

    public NodoEntero2(int valor) {
        this.valor = valor;
    }
}

public class ArbolAlturaPostorden {
    private NodoEntero2 raiz;

    // (asumí que insertar() ya está implementado igual que en el ejercicio anterior)

    public void postOrden() {
        // Completar
    }

    private void postOrdenRec(NodoEntero2 nodo) {
        // Completar: izquierda, derecha, imprimir valor
    }

    public int altura() {
        // Completar: llamar al método auxiliar desde la raíz
    }

    private int alturaRec(NodoEntero2 nodo) {
        // Completar: si el nodo es null, la altura es -1 (o 0, según el criterio que uses);
        // si no, es 1 + el máximo entre la altura del subárbol izquierdo y el derecho
        // (usa Math.max)
    }
}
```

## Ejercicio 3
Completa `ArbolContador`, que cuenta cuántos nodos tiene el árbol y cuántos son hojas
(nodos sin hijos).

```java
class NodoContador {
    int valor;
    NodoContador izquierdo;
    NodoContador derecho;

    public NodoContador(int valor) {
        this.valor = valor;
    }
}

public class ArbolContador {
    private NodoContador raiz;

    // (asumí que insertar() ya está implementado)

    public int contarNodos() {
        // Completar: llamar al método auxiliar desde la raíz
    }

    private int contarNodosRec(NodoContador nodo) {
        // Completar: si nodo es null, devolver 0; si no, 1 + los nodos de ambos subárboles
    }

    public int contarHojas() {
        // Completar
    }

    private int contarHojasRec(NodoContador nodo) {
        // Completar: si nodo es null, devolver 0;
        // si nodo no tiene ni izquierdo ni derecho, devolver 1;
        // si no, sumar las hojas de ambos subárboles
    }
}
```

## Ejercicio 4
Completa `ArbolBusqueda`, con un método `contiene(int valor)` que indique si un valor
existe en el árbol, recorriendo de forma eficiente según las reglas del BST (sin
recorrer todo el árbol innecesariamente).

```java
class NodoBusqueda {
    int valor;
    NodoBusqueda izquierdo;
    NodoBusqueda derecho;

    public NodoBusqueda(int valor) {
        this.valor = valor;
    }
}

public class ArbolBusqueda {
    private NodoBusqueda raiz;

    // (asumí que insertar() ya está implementado)

    public boolean contiene(int valor) {
        // Completar: llamar al método auxiliar desde la raíz
    }

    private boolean contieneRec(NodoBusqueda nodo, int valor) {
        // Completar: caso base (nodo null -> false); si coincide, true;
        // si el valor buscado es menor, seguir por la izquierda; si es mayor, por la derecha
    }
}
```

## Ejercicio 5
Completa `ArbolExtremos`, con métodos para obtener el valor mínimo y máximo del árbol
(recorriendo hacia la izquierda o derecha según corresponda, sin usar recursión).

```java
class NodoExtremo {
    int valor;
    NodoExtremo izquierdo;
    NodoExtremo derecho;

    public NodoExtremo(int valor) {
        this.valor = valor;
    }
}

public class ArbolExtremos {
    private NodoExtremo raiz;

    // (asumí que insertar() ya está implementado)

    public int obtenerMinimo() {
        // Completar: partir desde raiz y avanzar mientras haya hijo izquierdo (while),
        // devolver el valor del último nodo alcanzado
    }

    public int obtenerMaximo() {
        // Completar: análogo, pero avanzando por la derecha
    }
}
```

## Ejercicio 6
Completa `ArbolEliminador`, con un método `eliminar(int valor)` que borre un nodo del
árbol. Para simplificar, asumí que el valor a eliminar **siempre tiene como máximo un
hijo** (no hace falta manejar el caso de dos hijos).

```java
class NodoEliminable {
    int valor;
    NodoEliminable izquierdo;
    NodoEliminable derecho;

    public NodoEliminable(int valor) {
        this.valor = valor;
    }
}

public class ArbolEliminador {
    private NodoEliminable raiz;

    // (asumí que insertar() ya está implementado)

    public void eliminar(int valor) {
        // Completar: actualizar raiz usando eliminarRec(raiz, valor)
    }

    private NodoEliminable eliminarRec(NodoEliminable nodo, int valor) {
        if (nodo == null) {
            return null;
        }
        if (valor < nodo.valor) {
            nodo.izquierdo = eliminarRec(nodo.izquierdo, valor);
        } else if (valor > nodo.valor) {
            nodo.derecho = eliminarRec(nodo.derecho, valor);
        } else {
            // Completar: este es el nodo a eliminar.
            // Si no tiene hijo izquierdo, devolver el hijo derecho (puede ser null).
            // Si no tiene hijo derecho, devolver el hijo izquierdo.
        }
        return nodo;
    }
}
```

## Ejercicio 7
Completa `ArbolNivelPorNivel`, que recorre el árbol **por niveles** (BFS), usando una
`Queue<NodoNivel>`, e imprime los valores en el orden en que se visitan.

```java
import java.util.LinkedList;
import java.util.Queue;

class NodoNivel {
    int valor;
    NodoNivel izquierdo;
    NodoNivel derecho;

    public NodoNivel(int valor) {
        this.valor = valor;
    }
}

public class ArbolNivelPorNivel {
    private NodoNivel raiz;

    // (asumí que insertar() ya está implementado)

    public void recorrerPorNiveles() {
        if (raiz == null) {
            return;
        }

        Queue<NodoNivel> cola = new LinkedList<>();
        // Completar: agregar la raíz a la cola

        while (!cola.isEmpty()) {
            NodoNivel actual = cola.poll();
            System.out.print(actual.valor + " ");

            // Completar: si actual tiene hijo izquierdo, agregarlo a la cola;
            // si tiene hijo derecho, agregarlo también
        }
    }
}
```
