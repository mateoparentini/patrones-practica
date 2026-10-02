# Ejercicios — Pilas (Stack)

## Ejercicio 1
Completa `VerificadorParentesis`, que usa una `Stack<Character>` para comprobar si una
cadena tiene los paréntesis `(` y `)` correctamente balanceados.

```java
import java.util.Stack;

public class VerificadorParentesis {

    public boolean estaBalanceado(String expresion) {
        Stack<Character> pila = new Stack<>();

        for (char c : expresion.toCharArray()) {
            if (c == '(') {
                // Completar: apilar
            } else if (c == ')') {
                // Completar: si la pila está vacía, devolver false (no hay par);
                // si no, desapilar
            }
        }

        // Completar: devolver true solo si la pila quedó vacía al final
    }
}
```

## Ejercicio 2
Completa `HistorialAcciones`, que usa una `Stack<String>` para implementar deshacer
(undo) la última acción registrada.

```java
import java.util.Stack;

public class HistorialAcciones {
    private Stack<String> acciones = new Stack<>();

    public void registrarAccion(String accion) {
        // Completar
    }

    public String deshacerUltimaAccion() {
        // Completar: si la pila está vacía, devolver null;
        // si no, desapilar y devolver la acción deshecha
    }

    public String verUltimaAccion() {
        // Completar: devolver (sin eliminar) la última acción, o null si está vacía
    }
}
```

## Ejercicio 3
Completa `InversorTexto`, que usa una `Stack<Character>` para invertir un String.

```java
import java.util.Stack;

public class InversorTexto {

    public String invertir(String texto) {
        Stack<Character> pila = new Stack<>();

        for (char c : texto.toCharArray()) {
            // Completar: apilar cada carácter
        }

        StringBuilder resultado = new StringBuilder();
        while (!pila.isEmpty()) {
            // Completar: desapilar y agregar al resultado
        }

        return resultado.toString();
    }
}
```

## Ejercicio 4
Completa `EvaluadorPostfijo`, que usa una `Stack<Integer>` para evaluar una expresión
en notación postfija (por ejemplo, `"3 4 +"` da `7`), con operadores `+`, `-`, `*`.
Asumí que los tokens vienen separados por espacios.

```java
import java.util.Stack;

public class EvaluadorPostfijo {

    public int evaluar(String expresion) {
        Stack<Integer> pila = new Stack<>();
        String[] tokens = expresion.split(" ");

        for (String token : tokens) {
            if (token.equals("+") || token.equals("-") || token.equals("*")) {
                int b = pila.pop();
                int a = pila.pop();
                // Completar: calcular el resultado según el operador y apilarlo
            } else {
                // Completar: convertir el token a número (Integer.parseInt) y apilarlo
            }
        }

        return pila.pop();
    }
}
```

## Ejercicio 5
Completa `PilaConMinimo`, una pila de enteros que además permite obtener el valor
mínimo actual en tiempo constante, usando una segunda pila auxiliar.

```java
import java.util.Stack;

public class PilaConMinimo {
    private Stack<Integer> pilaPrincipal = new Stack<>();
    private Stack<Integer> pilaMinimos = new Stack<>();

    public void push(int valor) {
        pilaPrincipal.push(valor);
        // Completar: si pilaMinimos está vacía o "valor" es menor o igual al
        // mínimo actual, apilarlo también en pilaMinimos
    }

    public int pop() {
        int valor = pilaPrincipal.pop();
        // Completar: si "valor" es igual al tope de pilaMinimos, desapilarlo también de ahí
        return valor;
    }

    public int obtenerMinimo() {
        // Completar: devolver el tope de pilaMinimos
    }
}
```
