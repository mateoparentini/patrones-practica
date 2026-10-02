# Ejercicios — Patrón Builder

## Ejercicio 1
Completa `PizzaBuilder` para construir objetos `Pizza` (atributos: `tamano` String, `queso` boolean, `pepperoni` boolean) paso a paso, encadenando métodos.

```java
class Pizza {
    private String tamano;
    private boolean queso;
    private boolean pepperoni;

    public Pizza(String tamano, boolean queso, boolean pepperoni) {
        this.tamano = tamano;
        this.queso = queso;
        this.pepperoni = pepperoni;
    }

    @Override
    public String toString() {
        return "Pizza [tamano=" + tamano + ", queso=" + queso + ", pepperoni=" + pepperoni + "]";
    }
}

class PizzaBuilder {
    private String tamano;
    private boolean queso;
    private boolean pepperoni;

    public PizzaBuilder setTamano(String tamano) {
        // Completar: asignar y devolver this
    }

    public PizzaBuilder setQueso(boolean queso) {
        // Completar
    }

    public PizzaBuilder setPepperoni(boolean pepperoni) {
        // Completar
    }

    public Pizza build() {
        // Completar: devolver una nueva Pizza con los datos acumulados
    }
}
```

## Ejercicio 2
Completa `ComputadoraBuilder` para construir objetos `Computadora` (`cpu`, `ram`, `almacenamiento`, todos String), paso a paso.

```java
class Computadora {
    private String cpu;
    private String ram;
    private String almacenamiento;

    public Computadora(String cpu, String ram, String almacenamiento) {
        this.cpu = cpu;
        this.ram = ram;
        this.almacenamiento = almacenamiento;
    }

    @Override
    public String toString() {
        return "Computadora [cpu=" + cpu + ", ram=" + ram + ", almacenamiento=" + almacenamiento + "]";
    }
}

class ComputadoraBuilder {
    private String cpu;
    private String ram;
    private String almacenamiento;

    public ComputadoraBuilder setCpu(String cpu) {
        // Completar
    }

    public ComputadoraBuilder setRam(String ram) {
        // Completar
    }

    public ComputadoraBuilder setAlmacenamiento(String almacenamiento) {
        // Completar
    }

    public Computadora build() {
        // Completar
    }
}
```

## Ejercicio 3
Completa `PerfilBuilder` para construir un `PerfilUsuario` (`nombre`, `bio`, `edad` int), con `edad` opcional (si no se setea, debe valer 0).

```java
class PerfilUsuario {
    private String nombre;
    private String bio;
    private int edad;

    public PerfilUsuario(String nombre, String bio, int edad) {
        this.nombre = nombre;
        this.bio = bio;
        this.edad = edad;
    }

    @Override
    public String toString() {
        return "PerfilUsuario [nombre=" + nombre + ", bio=" + bio + ", edad=" + edad + "]";
    }
}

class PerfilBuilder {
    private String nombre;
    private String bio = "";
    private int edad = 0;

    public PerfilBuilder setNombre(String nombre) {
        // Completar
    }

    public PerfilBuilder setBio(String bio) {
        // Completar
    }

    public PerfilBuilder setEdad(int edad) {
        // Completar
    }

    public PerfilUsuario build() {
        // Completar
    }
}
```

## Ejercicio 4
Completa `ContratoBuilder` para construir un `Contrato` (`cliente`, `monto` double, `plazoMeses` int).

```java
class Contrato {
    private String cliente;
    private double monto;
    private int plazoMeses;

    public Contrato(String cliente, double monto, int plazoMeses) {
        this.cliente = cliente;
        this.monto = monto;
        this.plazoMeses = plazoMeses;
    }

    @Override
    public String toString() {
        return "Contrato [cliente=" + cliente + ", monto=" + monto + ", plazoMeses=" + plazoMeses + "]";
    }
}

class ContratoBuilder {
    private String cliente;
    private double monto;
    private int plazoMeses;

    public ContratoBuilder setCliente(String cliente) {
        // Completar
    }

    public ContratoBuilder setMonto(double monto) {
        // Completar
    }

    public ContratoBuilder setPlazoMeses(int plazoMeses) {
        // Completar
    }

    public Contrato build() {
        // Completar
    }
}
```

## Ejercicio 5
Completa `ViajeBuilder` para construir un `Viaje` (`destino`, `dias` int, `conHotel` boolean, `conVuelo` boolean).

```java
class Viaje {
    private String destino;
    private int dias;
    private boolean conHotel;
    private boolean conVuelo;

    public Viaje(String destino, int dias, boolean conHotel, boolean conVuelo) {
        this.destino = destino;
        this.dias = dias;
        this.conHotel = conHotel;
        this.conVuelo = conVuelo;
    }

    @Override
    public String toString() {
        return "Viaje [destino=" + destino + ", dias=" + dias + ", conHotel=" + conHotel + ", conVuelo=" + conVuelo + "]";
    }
}

class ViajeBuilder {
    private String destino;
    private int dias;
    private boolean conHotel;
    private boolean conVuelo;

    public ViajeBuilder setDestino(String destino) {
        // Completar
    }

    public ViajeBuilder setDias(int dias) {
        // Completar
    }

    public ViajeBuilder setConHotel(boolean conHotel) {
        // Completar
    }

    public ViajeBuilder setConVuelo(boolean conVuelo) {
        // Completar
    }

    public Viaje build() {
        // Completar
    }
}
```
