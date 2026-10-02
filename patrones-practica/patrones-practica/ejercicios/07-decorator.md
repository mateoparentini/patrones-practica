# Ejercicios — Patrón Decorator

## Ejercicio 1
Completa el decorador `ConAzucar` para la interfaz `Bebida` (`costo()` double, `descripcion()` String),
que agrega $0.3 al costo y " con azúcar" a la descripción.

```java
interface Bebida {
    double costo();
    String descripcion();
}

class CafeSimple implements Bebida {
    @Override
    public double costo() { return 2.0; }
    @Override
    public String descripcion() { return "Café"; }
}

abstract class BebidaDecorator implements Bebida {
    protected Bebida bebidaDecorada;

    public BebidaDecorator(Bebida bebida) {
        this.bebidaDecorada = bebida;
    }
}

class ConAzucar extends BebidaDecorator {
    public ConAzucar(Bebida bebida) {
        super(bebida);
    }

    @Override
    public double costo() {
        // Completar
    }

    @Override
    public String descripcion() {
        // Completar
    }
}
```

## Ejercicio 2
Completa el decorador `ConQueso` para `Hamburguesa` (`precio()` double, `ingredientes()` String),
que agrega $1.5 al precio y ", queso" a los ingredientes.

```java
interface Hamburguesa {
    double precio();
    String ingredientes();
}

class HamburguesaSimple implements Hamburguesa {
    @Override
    public double precio() { return 5.0; }
    @Override
    public String ingredientes() { return "Pan, carne"; }
}

abstract class HamburguesaDecorator implements Hamburguesa {
    protected Hamburguesa hamburguesaDecorada;

    public HamburguesaDecorator(Hamburguesa hamburguesa) {
        this.hamburguesaDecorada = hamburguesa;
    }
}

class ConQueso extends HamburguesaDecorator {
    public ConQueso(Hamburguesa hamburguesa) {
        super(hamburguesa);
    }

    @Override
    public double precio() {
        // Completar
    }

    @Override
    public String ingredientes() {
        // Completar
    }
}
```

## Ejercicio 3
Completa el decorador `ConValidacionLongitud` para `CampoTexto` (método `validar(String texto)`
que devuelve `boolean`), que además de la validación base, exige que el texto tenga máximo 50 caracteres.

```java
interface CampoTexto {
    boolean validar(String texto);
}

class CampoTextoSimple implements CampoTexto {
    @Override
    public boolean validar(String texto) {
        return texto != null && !texto.isEmpty();
    }
}

abstract class CampoTextoDecorator implements CampoTexto {
    protected CampoTexto campoDecorado;

    public CampoTextoDecorator(CampoTexto campo) {
        this.campoDecorado = campo;
    }
}

class ConValidacionLongitud extends CampoTextoDecorator {
    public ConValidacionLongitud(CampoTexto campo) {
        super(campo);
    }

    @Override
    public boolean validar(String texto) {
        // Completar: debe cumplir la validación base Y tener longitud <= 50
    }
}
```

## Ejercicio 4
Completa el decorador `ConDescuento` para `Producto` (`precio()` double, `nombre()` String),
que aplica un 10% de descuento sobre el precio.

```java
interface Producto {
    double precio();
    String nombre();
}

class ProductoSimple implements Producto {
    private String nombre;
    private double precio;

    public ProductoSimple(String nombre, double precio) {
        this.nombre = nombre;
        this.precio = precio;
    }

    @Override
    public double precio() { return precio; }
    @Override
    public String nombre() { return nombre; }
}

abstract class ProductoDecorator implements Producto {
    protected Producto productoDecorado;

    public ProductoDecorator(Producto producto) {
        this.productoDecorado = producto;
    }
}

class ConDescuento extends ProductoDecorator {
    public ConDescuento(Producto producto) {
        super(producto);
    }

    @Override
    public double precio() {
        // Completar: aplicar 10% de descuento
    }

    @Override
    public String nombre() {
        // Completar: devolver el nombre del producto decorado
    }
}
```

## Ejercicio 5
Completa el decorador `ConRegistro` (logging) para `Operacion` (método `ejecutar()`),
que imprime un mensaje antes y después de ejecutar la operación real.

```java
interface Operacion {
    void ejecutar();
}

class OperacionSimple implements Operacion {
    @Override
    public void ejecutar() {
        System.out.println("Ejecutando operación...");
    }
}

abstract class OperacionDecorator implements Operacion {
    protected Operacion operacionDecorada;

    public OperacionDecorator(Operacion operacion) {
        this.operacionDecorada = operacion;
    }
}

class ConRegistro extends OperacionDecorator {
    public ConRegistro(Operacion operacion) {
        super(operacion);
    }

    @Override
    public void ejecutar() {
        // Completar: imprimir "Inicio", ejecutar la operación decorada, imprimir "Fin"
    }
}
```
