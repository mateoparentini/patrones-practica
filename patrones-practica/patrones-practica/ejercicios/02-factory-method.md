# Ejercicios — Patrón Factory Method

## Ejercicio 1
Completa el sistema para crear distintos tipos de `Instrumento` musical.

* `Instrumento`: interfaz con `tocar()`.
* `Guitarra` y `Piano`: implementan `tocar()`.
* `InstrumentoFactory`: clase abstracta con `crearInstrumento()`.
* `GuitarraFactory` y `PianoFactory`: devuelven el instrumento correspondiente.

```java
interface Instrumento {
    void tocar();
}

class Guitarra implements Instrumento {
    @Override
    public void tocar() {
        System.out.println("Rasgueando la guitarra");
    }
}

class Piano implements Instrumento {
    @Override
    public void tocar() {
        System.out.println("Tocando el piano");
    }
}

abstract class InstrumentoFactory {
    // Completar: método abstracto de creación
}

class GuitarraFactory extends InstrumentoFactory {
    // Completar
}

class PianoFactory extends InstrumentoFactory {
    // Completar
}
```

## Ejercicio 2
Completa la fábrica de `MedioTransporte` para una app de logística.

* `MedioTransporte`: interfaz con `entregar()`.
* `Camion` y `Barco`: implementan `entregar()`.
* `TransporteFactory`: clase abstracta con `crearTransporte()`.
* `CamionFactory` y `BarcoFactory`: implementaciones concretas.

```java
interface MedioTransporte {
    void entregar();
}

class Camion implements MedioTransporte {
    @Override
    public void entregar() {
        System.out.println("Entregando por carretera");
    }
}

class Barco implements MedioTransporte {
    @Override
    public void entregar() {
        System.out.println("Entregando por mar");
    }
}

abstract class TransporteFactory {
    // Completar
}

class CamionFactory extends TransporteFactory {
    // Completar
}

class BarcoFactory extends TransporteFactory {
    // Completar
}
```

## Ejercicio 3
Completa la fábrica de `Bebida` para una cafetería.

* `Bebida`: interfaz con `preparar()`.
* `Cafe` y `Te`: implementan `preparar()`.
* `BebidaFactory`: clase abstracta con `crearBebida()`.
* `CafeFactory` y `TeFactory`: implementaciones concretas.

```java
interface Bebida {
    void preparar();
}

class Cafe implements Bebida {
    @Override
    public void preparar() {
        System.out.println("Preparando un café");
    }
}

class Te implements Bebida {
    @Override
    public void preparar() {
        System.out.println("Preparando un té");
    }
}

abstract class BebidaFactory {
    // Completar
}

class CafeFactory extends BebidaFactory {
    // Completar
}

class TeFactory extends BebidaFactory {
    // Completar
}
```

## Ejercicio 4
Completa la fábrica de `Figura` geométrica.

* `Figura`: interfaz con `dibujar()`.
* `Circulo` y `Cuadrado`: implementan `dibujar()`.
* `FiguraFactory`: clase abstracta con `crearFigura()`.
* `CirculoFactory` y `CuadradoFactory`: implementaciones concretas.

```java
interface Figura {
    void dibujar();
}

class Circulo implements Figura {
    @Override
    public void dibujar() {
        System.out.println("Dibujando un círculo");
    }
}

class Cuadrado implements Figura {
    @Override
    public void dibujar() {
        System.out.println("Dibujando un cuadrado");
    }
}

abstract class FiguraFactory {
    // Completar
}

class CirculoFactory extends FiguraFactory {
    // Completar
}

class CuadradoFactory extends FiguraFactory {
    // Completar
}
```

## Ejercicio 5
Completa la fábrica de `Documento` para un editor.

* `Documento`: interfaz con `abrir()`.
* `DocumentoTexto` y `DocumentoHoja`: implementan `abrir()`.
* `DocumentoFactory`: clase abstracta con `crearDocumento()`.
* `DocumentoTextoFactory` y `DocumentoHojaFactory`: implementaciones concretas.

```java
interface Documento {
    void abrir();
}

class DocumentoTexto implements Documento {
    @Override
    public void abrir() {
        System.out.println("Abriendo documento de texto");
    }
}

class DocumentoHoja implements Documento {
    @Override
    public void abrir() {
        System.out.println("Abriendo hoja de cálculo");
    }
}

abstract class DocumentoFactory {
    // Completar
}

class DocumentoTextoFactory extends DocumentoFactory {
    // Completar
}

class DocumentoHojaFactory extends DocumentoFactory {
    // Completar
}
```
