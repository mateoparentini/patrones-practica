# Ejercicios — Patrón Strategy

## Ejercicio 1
Completa el sistema de cálculo de impuestos con distintas estrategias.
Completa la interfaz `EstrategiaImpuesto` y la clase `CalculadoraImpuesto`.

```java
interface EstrategiaImpuesto {
    double calcular(double montoBase);
}

class ImpuestoGeneral implements EstrategiaImpuesto {
    @Override
    public double calcular(double montoBase) {
        return montoBase * 0.18;
    }
}

class ImpuestoReducido implements EstrategiaImpuesto {
    @Override
    public double calcular(double montoBase) {
        return montoBase * 0.05;
    }
}

class CalculadoraImpuesto {
    private EstrategiaImpuesto estrategia;

    public void setEstrategia(EstrategiaImpuesto estrategia) {
        // Completar
    }

    public double calcularImpuesto(double montoBase) {
        // Completar: validar que haya estrategia asignada (si no, lanzar
        // IllegalStateException("No se ha seleccionado una estrategia de impuesto"))
        // y delegar el cálculo
    }
}
```

## Ejercicio 2
Completa el sistema de descuentos de una tienda con distintas estrategias.

```java
interface EstrategiaDescuento {
    double aplicar(double precio);
}

class SinDescuento implements EstrategiaDescuento {
    @Override
    public double aplicar(double precio) {
        return precio;
    }
}

class DescuentoPorcentaje implements EstrategiaDescuento {
    private double porcentaje;

    public DescuentoPorcentaje(double porcentaje) {
        this.porcentaje = porcentaje;
    }

    @Override
    public double aplicar(double precio) {
        return precio - (precio * porcentaje / 100);
    }
}

class CarritoConDescuento {
    private EstrategiaDescuento estrategia;

    public void setEstrategia(EstrategiaDescuento estrategia) {
        // Completar
    }

    public double calcularPrecioFinal(double precio) {
        // Completar: validar estrategia no nula (lanzar IllegalStateException con
        // mensaje "No se ha seleccionado una estrategia de descuento") y delegar
    }
}
```

## Ejercicio 3
Completa el sistema de rutas de un GPS con distintas estrategias (más corta / más rápida).

```java
interface EstrategiaRuta {
    String calcularRuta(String origen, String destino);
}

class RutaMasCorta implements EstrategiaRuta {
    @Override
    public String calcularRuta(String origen, String destino) {
        return "Ruta más corta de " + origen + " a " + destino;
    }
}

class RutaMasRapida implements EstrategiaRuta {
    @Override
    public String calcularRuta(String origen, String destino) {
        return "Ruta más rápida de " + origen + " a " + destino;
    }
}

class NavegadorGPS {
    private EstrategiaRuta estrategia;

    public void setEstrategia(EstrategiaRuta estrategia) {
        // Completar
    }

    public String obtenerRuta(String origen, String destino) {
        // Completar: validar estrategia no nula (lanzar IllegalStateException con
        // mensaje "No se ha seleccionado una estrategia de ruta") y delegar
    }
}
```

## Ejercicio 4
Completa el sistema de compresión de archivos con distintas estrategias (ZIP / RAR).

```java
interface EstrategiaCompresion {
    String comprimir(String nombreArchivo);
}

class CompresionZip implements EstrategiaCompresion {
    @Override
    public String comprimir(String nombreArchivo) {
        return nombreArchivo + ".zip";
    }
}

class CompresionRar implements EstrategiaCompresion {
    @Override
    public String comprimir(String nombreArchivo) {
        return nombreArchivo + ".rar";
    }
}

class CompresorArchivos {
    private EstrategiaCompresion estrategia;

    public void setEstrategia(EstrategiaCompresion estrategia) {
        // Completar
    }

    public String comprimirArchivo(String nombreArchivo) {
        // Completar: validar estrategia no nula (lanzar IllegalStateException con
        // mensaje "No se ha seleccionado una estrategia de compresión") y delegar
    }
}
```

## Ejercicio 5
Completa el sistema de ordenamiento de una lista con distintas estrategias
(ascendente / descendente), usando `List<Integer>`.

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

interface EstrategiaOrdenamiento {
    List<Integer> ordenar(List<Integer> lista);
}

class OrdenAscendente implements EstrategiaOrdenamiento {
    @Override
    public List<Integer> ordenar(List<Integer> lista) {
        List<Integer> copia = new ArrayList<>(lista);
        Collections.sort(copia);
        return copia;
    }
}

class OrdenDescendente implements EstrategiaOrdenamiento {
    @Override
    public List<Integer> ordenar(List<Integer> lista) {
        List<Integer> copia = new ArrayList<>(lista);
        Collections.sort(copia, Collections.reverseOrder());
        return copia;
    }
}

class OrdenadorLista {
    private EstrategiaOrdenamiento estrategia;

    public void setEstrategia(EstrategiaOrdenamiento estrategia) {
        // Completar
    }

    public List<Integer> ordenarLista(List<Integer> lista) {
        // Completar: validar estrategia no nula (lanzar IllegalStateException con
        // mensaje "No se ha seleccionado una estrategia de ordenamiento") y delegar
    }
}
```
