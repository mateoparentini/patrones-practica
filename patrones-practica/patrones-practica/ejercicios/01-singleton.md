# Ejercicios — Patrón Singleton

## Ejercicio 1
Completa la clase `GestorSesion` para implementar el patrón Singleton.
La clase debe mantener una única instancia y un atributo `usuarioActivo` (String).

* `getInstance()`: obtiene la única instancia. Si no existe, la crea.
* `iniciarSesion(String usuario)`: asigna el usuario activo.
* `cerrarSesion()`: pone `usuarioActivo` en `null`.
* `getUsuarioActivo()`: devuelve el usuario activo.

```java
public class GestorSesion {
    private static GestorSesion instance;
    private String usuarioActivo;

    private GestorSesion() {
        // Completar
    }

    public static GestorSesion getInstance() {
        // Completar
    }

    public void iniciarSesion(String usuario) {
        // Completar
    }

    public void cerrarSesion() {
        // Completar
    }

    public String getUsuarioActivo() {
        // Completar
    }
}
```

## Ejercicio 2
Completa `ContadorVisitas` como Singleton. Debe llevar la cuenta de visitas a una página.

* `getInstance()`: única instancia.
* `registrarVisita()`: incrementa el contador en 1.
* `obtenerTotalVisitas()`: devuelve el total.

```java
public class ContadorVisitas {
    private static ContadorVisitas instancia;
    private int total;

    private ContadorVisitas() {
        // Completar
    }

    public static ContadorVisitas getInstance() {
        // Completar
    }

    public void registrarVisita() {
        // Completar
    }

    public int obtenerTotalVisitas() {
        // Completar
    }
}
```

## Ejercicio 3
Completa `ConfiguracionApp`, un Singleton que guarda pares clave-valor de configuración
usando un `Map<String, String>`.

* `getInstance()`: única instancia (el mapa se crea vacío en el constructor).
* `set(String clave, String valor)`: guarda/actualiza un valor.
* `get(String clave)`: devuelve el valor asociado o `null` si no existe.

```java
import java.util.HashMap;
import java.util.Map;

public class ConfiguracionApp {
    private static ConfiguracionApp instancia;
    private Map<String, String> valores;

    private ConfiguracionApp() {
        // Completar
    }

    public static ConfiguracionApp getInstance() {
        // Completar
    }

    public void set(String clave, String valor) {
        // Completar
    }

    public String get(String clave) {
        // Completar
    }
}
```

## Ejercicio 4
Completa `CarritoCompras` como Singleton compartido entre distintas partes de una tienda.
Debe mantener una lista de productos (`List<String>`).

* `getInstance()`: única instancia.
* `agregarProducto(String producto)`: agrega un producto a la lista.
* `vaciarCarrito()`: elimina todos los productos.
* `cantidadProductos()`: devuelve cuántos productos hay.

```java
import java.util.ArrayList;
import java.util.List;

public class CarritoCompras {
    private static CarritoCompras instancia;
    private List<String> productos;

    private CarritoCompras() {
        // Completar
    }

    public static CarritoCompras getInstance() {
        // Completar
    }

    public void agregarProducto(String producto) {
        // Completar
    }

    public void vaciarCarrito() {
        // Completar
    }

    public int cantidadProductos() {
        // Completar
    }
}
```

## Ejercicio 5
Completa `Impresora3D`, Singleton que simula una cola de trabajos de impresión (`List<String>`).

* `getInstance()`: única instancia.
* `encolarTrabajo(String nombreArchivo)`: agrega un trabajo al final de la cola.
* `imprimirSiguiente()`: elimina y devuelve el primer trabajo de la cola, o `null` si está vacía.

```java
import java.util.LinkedList;

public class Impresora3D {
    private static Impresora3D instancia;
    private LinkedList<String> cola;

    private Impresora3D() {
        // Completar
    }

    public static Impresora3D getInstance() {
        // Completar
    }

    public void encolarTrabajo(String nombreArchivo) {
        // Completar
    }

    public String imprimirSiguiente() {
        // Completar: si la cola está vacía devolver null
    }
}
```
