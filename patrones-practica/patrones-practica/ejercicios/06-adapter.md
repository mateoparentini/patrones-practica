# Ejercicios — Patrón Adapter

## Ejercicio 1
La app espera la interfaz `Impresora` (método `imprimir()`), pero existe una impresora
antigua `ImpresoraLegacy` con un método distinto `imprimirEnPapel()`. Completa el adaptador.

```java
interface Impresora {
    void imprimir();
}

class ImpresoraLegacy {
    public void imprimirEnPapel() {
        System.out.println("Imprimiendo con impresora antigua...");
    }
}

class ImpresoraAdapter implements Impresora {
    private ImpresoraLegacy impresoraLegacy;

    public ImpresoraAdapter(ImpresoraLegacy impresoraLegacy) {
        this.impresoraLegacy = impresoraLegacy;
    }

    @Override
    public void imprimir() {
        // Completar: delegar al método real de ImpresoraLegacy
    }
}
```

## Ejercicio 2
La app espera `ReproductorMedia` (método `reproducir()`), pero hay una clase externa
`ReproductorMP4` con el método `playVideo()`. Completa el adaptador.

```java
interface ReproductorMedia {
    void reproducir();
}

class ReproductorMP4 {
    public void playVideo() {
        System.out.println("Reproduciendo video MP4...");
    }
}

class ReproductorAdapter implements ReproductorMedia {
    private ReproductorMP4 reproductorMP4;

    public ReproductorAdapter(ReproductorMP4 reproductorMP4) {
        this.reproductorMP4 = reproductorMP4;
    }

    @Override
    public void reproducir() {
        // Completar
    }
}
```

## Ejercicio 3
La app espera `SensorTemperatura` (método `leerCelsius()` que devuelve `double`), pero
el sensor de un proveedor externo `SensorFahrenheit` solo tiene `getFahrenheit()`.
Completa el adaptador, que debe convertir Fahrenheit a Celsius: `(f - 32) / 1.8`.

```java
interface SensorTemperatura {
    double leerCelsius();
}

class SensorFahrenheit {
    public double getFahrenheit() {
        return 98.6; // valor de ejemplo
    }
}

class SensorAdapter implements SensorTemperatura {
    private SensorFahrenheit sensorFahrenheit;

    public SensorAdapter(SensorFahrenheit sensorFahrenheit) {
        this.sensorFahrenheit = sensorFahrenheit;
    }

    @Override
    public double leerCelsius() {
        // Completar: obtener Fahrenheit y convertir a Celsius
    }
}
```

## Ejercicio 4
La app espera `Notificador` (método `enviar(String mensaje)`), pero existe un servicio
externo `ServicioSMSExterno` con el método `sendText(String texto)`. Completa el adaptador.

```java
interface Notificador {
    void enviar(String mensaje);
}

class ServicioSMSExterno {
    public void sendText(String texto) {
        System.out.println("SMS enviado: " + texto);
    }
}

class SMSAdapter implements Notificador {
    private ServicioSMSExterno servicioSMS;

    public SMSAdapter(ServicioSMSExterno servicioSMS) {
        this.servicioSMS = servicioSMS;
    }

    @Override
    public void enviar(String mensaje) {
        // Completar
    }
}
```

## Ejercicio 5
La app espera `LectorArchivo` (método `leer()` que devuelve `String`), pero una librería
externa `LectorXMLAntiguo` solo tiene `parseXML()` que devuelve `String`. Completa el adaptador.

```java
interface LectorArchivo {
    String leer();
}

class LectorXMLAntiguo {
    public String parseXML() {
        return "<datos>contenido del xml</datos>";
    }
}

class LectorXMLAdapter implements LectorArchivo {
    private LectorXMLAntiguo lectorXML;

    public LectorXMLAdapter(LectorXMLAntiguo lectorXML) {
        this.lectorXML = lectorXML;
    }

    @Override
    public String leer() {
        // Completar
    }
}
```
