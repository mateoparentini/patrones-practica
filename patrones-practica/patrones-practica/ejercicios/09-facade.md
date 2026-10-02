# Ejercicios — Patrón Facade (7 ejercicios — tema a reforzar)

## Ejercicio 1
Un sistema de compra online tiene los subsistemas `Inventario`, `Pago` y `Envio`
(ya implementados). Completa `TiendaFacade` con el método
`void comprar(String producto, int cantidad, double monto, String direccion)`
que orqueste los tres subsistemas en orden y al final imprima
`"Compra completada: " + cantidad + " x " + producto`.

```java
class Inventario {
    public void reservarStock(String producto, int cantidad) {
        System.out.println("Reservando " + cantidad + " de " + producto);
    }
}

class Pago {
    public void cobrar(double monto) {
        System.out.println("Cobrando $" + monto);
    }
}

class Envio {
    public void programarEnvio(String direccion) {
        System.out.println("Programando envío a " + direccion);
    }
}

class TiendaFacade {
    private Inventario inventario = new Inventario();
    private Pago pago = new Pago();
    private Envio envio = new Envio();

    public void comprar(String producto, int cantidad, double monto, String direccion) {
        // Completar: llamar a los 3 subsistemas en orden y luego imprimir el mensaje final
    }
}
```

## Ejercicio 2
Un sistema de check-in de aeropuerto tiene los subsistemas `ValidacionPasaporte`,
`AsignacionAsiento` y `EmisionTarjetaEmbarque`. Completa `CheckInFacade` con el método
`void realizarCheckIn(String pasajero, String vuelo)` que orqueste los tres pasos y al
final imprima `"Check-in completado para " + pasajero`.

```java
class ValidacionPasaporte {
    public void validar(String pasajero) {
        System.out.println("Validando pasaporte de " + pasajero);
    }
}

class AsignacionAsiento {
    public void asignar(String vuelo) {
        System.out.println("Asignando asiento para el vuelo " + vuelo);
    }
}

class EmisionTarjetaEmbarque {
    public void emitir(String pasajero) {
        System.out.println("Emitiendo tarjeta de embarque para " + pasajero);
    }
}

class CheckInFacade {
    private ValidacionPasaporte validacion = new ValidacionPasaporte();
    private AsignacionAsiento asiento = new AsignacionAsiento();
    private EmisionTarjetaEmbarque tarjeta = new EmisionTarjetaEmbarque();

    public void realizarCheckIn(String pasajero, String vuelo) {
        // Completar
    }
}
```

## Ejercicio 3
Un sistema de matrícula universitaria tiene `VerificacionRequisitos`, `RegistroCurso`
y `GeneracionFactura`. Completa `MatriculaFacade` con
`void matricular(String alumno, String curso, double costo)` que orqueste los tres pasos
y al final imprima `"Matrícula completada para " + alumno + " en " + curso`.

```java
class VerificacionRequisitos {
    public void verificar(String alumno, String curso) {
        System.out.println("Verificando requisitos de " + alumno + " para " + curso);
    }
}

class RegistroCurso {
    public void registrar(String alumno, String curso) {
        System.out.println("Registrando a " + alumno + " en " + curso);
    }
}

class GeneracionFactura {
    public void generar(double costo) {
        System.out.println("Generando factura por $" + costo);
    }
}

class MatriculaFacade {
    private VerificacionRequisitos verificacion = new VerificacionRequisitos();
    private RegistroCurso registro = new RegistroCurso();
    private GeneracionFactura factura = new GeneracionFactura();

    public void matricular(String alumno, String curso, double costo) {
        // Completar
    }
}
```

## Ejercicio 4
Un sistema de reserva de hotel tiene `DisponibilidadHabitacion`, `PagoReserva` y
`ConfirmacionReserva`. Completa `HotelFacade` con
`void reservarHabitacion(String huesped, String tipoHabitacion, double monto)` que
orqueste los tres pasos y al final imprima `"Reserva confirmada para " + huesped`.

```java
class DisponibilidadHabitacion {
    public void verificar(String tipoHabitacion) {
        System.out.println("Verificando disponibilidad de " + tipoHabitacion);
    }
}

class PagoReserva {
    public void procesar(double monto) {
        System.out.println("Procesando pago de $" + monto);
    }
}

class ConfirmacionReserva {
    public void confirmar(String huesped) {
        System.out.println("Confirmando reserva de " + huesped);
    }
}

class HotelFacade {
    private DisponibilidadHabitacion disponibilidad = new DisponibilidadHabitacion();
    private PagoReserva pago = new PagoReserva();
    private ConfirmacionReserva confirmacion = new ConfirmacionReserva();

    public void reservarHabitacion(String huesped, String tipoHabitacion, double monto) {
        // Completar
    }
}
```

## Ejercicio 5
Un sistema de streaming tiene `AutenticacionUsuario`, `CargaContenido` y
`RegistroReproduccion`. Completa `StreamingFacade` con
`void reproducirContenido(String usuario, String titulo)` que orqueste los tres pasos
y al final imprima `"Reproduciendo " + titulo + " para " + usuario`.

```java
class AutenticacionUsuario {
    public void autenticar(String usuario) {
        System.out.println("Autenticando a " + usuario);
    }
}

class CargaContenido {
    public void cargar(String titulo) {
        System.out.println("Cargando contenido: " + titulo);
    }
}

class RegistroReproduccion {
    public void registrar(String usuario, String titulo) {
        System.out.println("Registrando reproducción de " + usuario);
    }
}

class StreamingFacade {
    private AutenticacionUsuario autenticacion = new AutenticacionUsuario();
    private CargaContenido carga = new CargaContenido();
    private RegistroReproduccion registro = new RegistroReproduccion();

    public void reproducirContenido(String usuario, String titulo) {
        // Completar
    }
}
```

## Ejercicio 6
Un sistema de taller mecánico tiene `DiagnosticoVehiculo`, `ReparacionVehiculo` y
`FacturacionTaller`. Completa `TallerFacade` con
`void atenderVehiculo(String placa, String falla, double costo)` que orqueste los tres
pasos y al final imprima `"Vehículo " + placa + " listo para retirar"`.

```java
class DiagnosticoVehiculo {
    public void diagnosticar(String placa, String falla) {
        System.out.println("Diagnosticando " + placa + ": " + falla);
    }
}

class ReparacionVehiculo {
    public void reparar(String placa) {
        System.out.println("Reparando vehículo " + placa);
    }
}

class FacturacionTaller {
    public void facturar(double costo) {
        System.out.println("Facturando $" + costo);
    }
}

class TallerFacade {
    private DiagnosticoVehiculo diagnostico = new DiagnosticoVehiculo();
    private ReparacionVehiculo reparacion = new ReparacionVehiculo();
    private FacturacionTaller facturacion = new FacturacionTaller();

    public void atenderVehiculo(String placa, String falla, double costo) {
        // Completar
    }
}
```

## Ejercicio 7
Un sistema de biblioteca tiene `VerificacionSocio`, `RegistroPrestamo` y
`NotificacionDevolucion`. Completa `BibliotecaFacade` con
`void prestarLibro(String socio, String libro, String fechaDevolucion)` que orqueste
los tres pasos y al final imprima `"Préstamo registrado: " + libro + " a " + socio`.

```java
class VerificacionSocio {
    public void verificar(String socio) {
        System.out.println("Verificando membresía de " + socio);
    }
}

class RegistroPrestamo {
    public void registrar(String socio, String libro) {
        System.out.println("Registrando préstamo de " + libro + " a " + socio);
    }
}

class NotificacionDevolucion {
    public void notificar(String socio, String fechaDevolucion) {
        System.out.println("Fecha de devolución para " + socio + ": " + fechaDevolucion);
    }
}

class BibliotecaFacade {
    private VerificacionSocio verificacion = new VerificacionSocio();
    private RegistroPrestamo prestamo = new RegistroPrestamo();
    private NotificacionDevolucion notificacion = new NotificacionDevolucion();

    public void prestarLibro(String socio, String libro, String fechaDevolucion) {
        // Completar
    }
}
```
