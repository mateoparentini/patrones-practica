# Ejercicios — Patrón Observer

## Ejercicio 1
Completa `CanalYoutube` (sujeto) que notifica a sus `Suscriptor` (observadores) cuando
sube un nuevo video.

```java
import java.util.ArrayList;
import java.util.List;

interface Suscriptor {
    void notificar(String tituloVideo);
}

interface Canal {
    void suscribir(Suscriptor suscriptor);
    void desuscribir(Suscriptor suscriptor);
    void notificarSuscriptores();
}

class CanalYoutube implements Canal {
    private List<Suscriptor> suscriptores = new ArrayList<>();
    private String ultimoVideo;

    @Override
    public void suscribir(Suscriptor suscriptor) {
        // Completar
    }

    @Override
    public void desuscribir(Suscriptor suscriptor) {
        // Completar
    }

    @Override
    public void notificarSuscriptores() {
        // Completar: recorrer la lista y llamar a notificar() de cada uno
    }

    public void subirVideo(String titulo) {
        // Completar: asignar ultimoVideo y llamar a notificarSuscriptores()
    }
}
```

## Ejercicio 2
Completa `AccionBolsa` (sujeto) que notifica a sus `InversorObservador` cuando cambia
el precio.

```java
import java.util.ArrayList;
import java.util.List;

interface InversorObservador {
    void actualizarPrecio(double nuevoPrecio);
}

interface SujetoAccion {
    void agregarInversor(InversorObservador inversor);
    void eliminarInversor(InversorObservador inversor);
    void notificarInversores();
}

class AccionBolsa implements SujetoAccion {
    private List<InversorObservador> inversores = new ArrayList<>();
    private double precio;

    @Override
    public void agregarInversor(InversorObservador inversor) {
        // Completar
    }

    @Override
    public void eliminarInversor(InversorObservador inversor) {
        // Completar
    }

    @Override
    public void notificarInversores() {
        // Completar
    }

    public void setPrecio(double precio) {
        // Completar: asignar precio y notificar a los inversores
    }
}
```

## Ejercicio 3
Completa `CarritoCompra` (sujeto) que notifica a `ObservadorCarrito` cuando cambia la
cantidad de ítems.

```java
import java.util.ArrayList;
import java.util.List;

interface ObservadorCarrito {
    void actualizar(int cantidadItems);
}

interface SujetoCarrito {
    void agregarObservador(ObservadorCarrito observador);
    void eliminarObservador(ObservadorCarrito observador);
    void notificarObservadores();
}

class CarritoCompra implements SujetoCarrito {
    private List<ObservadorCarrito> observadores = new ArrayList<>();
    private int cantidadItems = 0;

    @Override
    public void agregarObservador(ObservadorCarrito observador) {
        // Completar
    }

    @Override
    public void eliminarObservador(ObservadorCarrito observador) {
        // Completar
    }

    @Override
    public void notificarObservadores() {
        // Completar
    }

    public void agregarItem() {
        // Completar: incrementar cantidadItems y notificar
    }
}
```

## Ejercicio 4
Completa `EstacionMeteorologica` (sujeto) que notifica a `PantallaClima` la humedad
actual.

```java
import java.util.ArrayList;
import java.util.List;

interface PantallaClima {
    void actualizar(float humedad);
}

interface SujetoClima {
    void agregarPantalla(PantallaClima pantalla);
    void eliminarPantalla(PantallaClima pantalla);
    void notificarPantallas();
}

class EstacionMeteorologica implements SujetoClima {
    private List<PantallaClima> pantallas = new ArrayList<>();
    private float humedad;

    @Override
    public void agregarPantalla(PantallaClima pantalla) {
        // Completar
    }

    @Override
    public void eliminarPantalla(PantallaClima pantalla) {
        // Completar
    }

    @Override
    public void notificarPantallas() {
        // Completar
    }

    public void setHumedad(float humedad) {
        // Completar
    }
}
```

## Ejercicio 5
Completa `SistemaTickets` (sujeto) que notifica a `AgenteSoporte` cuando se crea un
nuevo ticket.

```java
import java.util.ArrayList;
import java.util.List;

interface AgenteSoporte {
    void notificarNuevoTicket(String descripcion);
}

interface SujetoTickets {
    void agregarAgente(AgenteSoporte agente);
    void eliminarAgente(AgenteSoporte agente);
    void notificarAgentes();
}

class SistemaTickets implements SujetoTickets {
    private List<AgenteSoporte> agentes = new ArrayList<>();
    private String ultimoTicket;

    @Override
    public void agregarAgente(AgenteSoporte agente) {
        // Completar
    }

    @Override
    public void eliminarAgente(AgenteSoporte agente) {
        // Completar
    }

    @Override
    public void notificarAgentes() {
        // Completar
    }

    public void crearTicket(String descripcion) {
        // Completar
    }
}
```
