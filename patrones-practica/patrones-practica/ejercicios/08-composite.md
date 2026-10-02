# Ejercicios — Patrón Composite

## Ejercicio 1
Completa `Carpeta` (puede contener `Archivo` u otras `Carpeta`) para calcular el tamaño
total, siguiendo el mismo modelo que un sistema de archivos.

```java
import java.util.ArrayList;
import java.util.List;

interface ElementoArchivo {
    int tamano();
}

class Archivo implements ElementoArchivo {
    private int tamano;

    public Archivo(int tamano) {
        this.tamano = tamano;
    }

    @Override
    public int tamano() {
        return tamano;
    }
}

class Carpeta implements ElementoArchivo {
    private List<ElementoArchivo> elementos = new ArrayList<>();

    public void agregar(ElementoArchivo elemento) {
        // Completar
    }

    public void eliminar(ElementoArchivo elemento) {
        // Completar
    }

    @Override
    public int tamano() {
        // Completar: sumar el tamaño de todos los elementos
    }
}
```

## Ejercicio 2
Completa `UnidadMilitar` (puede contener `Soldado` u otras unidades) para calcular el
total de efectivos.

```java
import java.util.ArrayList;
import java.util.List;

interface ElementoMilitar {
    int cantidadEfectivos();
}

class Soldado implements ElementoMilitar {
    @Override
    public int cantidadEfectivos() {
        return 1;
    }
}

class UnidadMilitar implements ElementoMilitar {
    private List<ElementoMilitar> miembros = new ArrayList<>();

    public void agregar(ElementoMilitar elemento) {
        // Completar
    }

    public void eliminar(ElementoMilitar elemento) {
        // Completar
    }

    @Override
    public int cantidadEfectivos() {
        // Completar
    }
}
```

## Ejercicio 3
Completa `Menu` de restaurante (puede contener `PlatoIndividual` u otros `Menu`
—por ejemplo, un combo— ) para calcular el precio total.

```java
import java.util.ArrayList;
import java.util.List;

interface ElementoMenu {
    double precio();
}

class PlatoIndividual implements ElementoMenu {
    private double precio;

    public PlatoIndividual(double precio) {
        this.precio = precio;
    }

    @Override
    public double precio() {
        return precio;
    }
}

class Menu implements ElementoMenu {
    private List<ElementoMenu> items = new ArrayList<>();

    public void agregar(ElementoMenu item) {
        // Completar
    }

    public void eliminar(ElementoMenu item) {
        // Completar
    }

    @Override
    public double precio() {
        // Completar
    }
}
```

## Ejercicio 4
Completa `Equipo` de trabajo (puede contener `Persona` u otros `Equipo` —subequipos—)
para calcular el costo total de nómina.

```java
import java.util.ArrayList;
import java.util.List;

interface ElementoEquipo {
    double costoNomina();
}

class Persona implements ElementoEquipo {
    private double salario;

    public Persona(double salario) {
        this.salario = salario;
    }

    @Override
    public double costoNomina() {
        return salario;
    }
}

class Equipo implements ElementoEquipo {
    private List<ElementoEquipo> miembros = new ArrayList<>();

    public void agregar(ElementoEquipo miembro) {
        // Completar
    }

    public void eliminar(ElementoEquipo miembro) {
        // Completar
    }

    @Override
    public double costoNomina() {
        // Completar
    }
}
```

## Ejercicio 5
Completa `Categoria` de un catálogo de productos (puede contener `ProductoCatalogo` u
otras `Categoria` —subcategorías—) para contar cuántos productos hay en total.

```java
import java.util.ArrayList;
import java.util.List;

interface ElementoCatalogo {
    int contarProductos();
}

class ProductoCatalogo implements ElementoCatalogo {
    @Override
    public int contarProductos() {
        return 1;
    }
}

class Categoria implements ElementoCatalogo {
    private List<ElementoCatalogo> elementos = new ArrayList<>();

    public void agregar(ElementoCatalogo elemento) {
        // Completar
    }

    public void eliminar(ElementoCatalogo elemento) {
        // Completar
    }

    @Override
    public int contarProductos() {
        // Completar
    }
}
```
