# Ejercicios — Patrón Prototype (7 ejercicios — tema a reforzar)

## Ejercicio 1
Completa `Empleado` para que pueda clonarse a sí mismo, conservando `nombre` y `puesto`.

```java
interface EmpleadoClonable {
    EmpleadoClonable clonar();
}

class Empleado implements EmpleadoClonable {
    private String nombre;
    private String puesto;

    public Empleado(String nombre, String puesto) {
        this.nombre = nombre;
        this.puesto = puesto;
    }

    @Override
    public EmpleadoClonable clonar() {
        // Completar: crear y devolver un nuevo Empleado con los mismos datos
    }

    @Override
    public String toString() {
        return nombre + " - " + puesto;
    }
}
```

## Ejercicio 2
Completa `Personaje` de un videojuego (`nombre`, `nivel` int, `vida` int) para que soporte clonación.
El clon debe ser un objeto distinto al original.

```java
interface PersonajeClonable {
    PersonajeClonable clonar();
}

class Personaje implements PersonajeClonable {
    private String nombre;
    private int nivel;
    private int vida;

    public Personaje(String nombre, int nivel, int vida) {
        this.nombre = nombre;
        this.nivel = nivel;
        this.vida = vida;
    }

    @Override
    public PersonajeClonable clonar() {
        // Completar
    }

    public void setVida(int vida) {
        this.vida = vida;
    }

    @Override
    public String toString() {
        return nombre + " (nivel " + nivel + ", vida " + vida + ")";
    }
}
```

## Ejercicio 3
Completa `Plantilla` de documento (`titulo`, `contenido`) con soporte de clonación,
usada para generar varios documentos a partir de una misma base.

```java
interface PlantillaClonable {
    PlantillaClonable clonar();
}

class Plantilla implements PlantillaClonable {
    private String titulo;
    private String contenido;

    public Plantilla(String titulo, String contenido) {
        this.titulo = titulo;
        this.contenido = contenido;
    }

    @Override
    public PlantillaClonable clonar() {
        // Completar
    }

    public void setTitulo(String titulo) {
        this.titulo = titulo;
    }

    @Override
    public String toString() {
        return titulo + ": " + contenido;
    }
}
```

## Ejercicio 4
Completa `Receta` de cocina (`nombre`, `porciones` int) con clonación, de forma que
al clonar una receta se pueda ajustar las porciones sin afectar a la original.

```java
interface RecetaClonable {
    RecetaClonable clonar();
}

class Receta implements RecetaClonable {
    private String nombre;
    private int porciones;

    public Receta(String nombre, int porciones) {
        this.nombre = nombre;
        this.porciones = porciones;
    }

    @Override
    public RecetaClonable clonar() {
        // Completar
    }

    public void setPorciones(int porciones) {
        this.porciones = porciones;
    }

    @Override
    public String toString() {
        return nombre + " (" + porciones + " porciones)";
    }
}
```

## Ejercicio 5
Completa `Enemigo` (`tipo`, `puntosVida` int, `dano` int) con clonación, para generar
varios enemigos iguales en un videojuego a partir de un prototipo.

```java
interface EnemigoClonable {
    EnemigoClonable clonar();
}

class Enemigo implements EnemigoClonable {
    private String tipo;
    private int puntosVida;
    private int dano;

    public Enemigo(String tipo, int puntosVida, int dano) {
        this.tipo = tipo;
        this.puntosVida = puntosVida;
        this.dano = dano;
    }

    @Override
    public EnemigoClonable clonar() {
        // Completar
    }

    @Override
    public String toString() {
        return tipo + " [vida=" + puntosVida + ", daño=" + dano + "]";
    }
}
```

## Ejercicio 6
Completa `Oferta` comercial (`producto`, `descuento` double) con clonación, de manera
que se puedan generar variantes de una oferta base para distintos productos.

```java
interface OfertaClonable {
    OfertaClonable clonar();
}

class Oferta implements OfertaClonable {
    private String producto;
    private double descuento;

    public Oferta(String producto, double descuento) {
        this.producto = producto;
        this.descuento = descuento;
    }

    @Override
    public OfertaClonable clonar() {
        // Completar
    }

    public void setProducto(String producto) {
        this.producto = producto;
    }

    @Override
    public String toString() {
        return producto + " (" + descuento + "% off)";
    }
}
```

## Ejercicio 7
Completa `ConfiguracionJuego` (`dificultad`, `volumen` int, `pantallaCompleta` boolean)
con clonación, para poder tener distintos perfiles de configuración a partir de uno base.

```java
interface ConfiguracionClonable {
    ConfiguracionClonable clonar();
}

class ConfiguracionJuego implements ConfiguracionClonable {
    private String dificultad;
    private int volumen;
    private boolean pantallaCompleta;

    public ConfiguracionJuego(String dificultad, int volumen, boolean pantallaCompleta) {
        this.dificultad = dificultad;
        this.volumen = volumen;
        this.pantallaCompleta = pantallaCompleta;
    }

    @Override
    public ConfiguracionClonable clonar() {
        // Completar
    }

    @Override
    public String toString() {
        return dificultad + ", vol=" + volumen + ", fullscreen=" + pantallaCompleta;
    }
}
```
