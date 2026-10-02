# Ejercicios — Patrón Proxy (7 ejercicios — tema a reforzar)

## Ejercicio 1
Completa `ProxyArchivo`, que controla el acceso a un `ArchivoReal` (carga costosa, solo
se crea cuando alguien pide verlo por primera vez — Proxy Virtual).

```java
interface Archivo {
    void mostrar();
}

class ArchivoReal implements Archivo {
    private String nombre;

    public ArchivoReal(String nombre) {
        this.nombre = nombre;
        System.out.println("Cargando archivo pesado: " + nombre);
    }

    @Override
    public void mostrar() {
        System.out.println("Mostrando: " + nombre);
    }
}

class ProxyArchivo implements Archivo {
    private String nombre;
    private ArchivoReal archivoReal;

    public ProxyArchivo(String nombre) {
        this.nombre = nombre;
    }

    @Override
    public void mostrar() {
        // Completar: crear archivoReal solo si todavía es null, y luego mostrarlo
    }
}
```

## Ejercicio 2
Completa `ProxyCuentaBancaria`, que controla el acceso a `CuentaBancariaReal` según el
PIN ingresado. Si el PIN es correcto, delega la operación; si no, imprime
`"PIN incorrecto, acceso denegado"`.

```java
interface CuentaBancaria {
    void retirar(double monto);
}

class CuentaBancariaReal implements CuentaBancaria {
    @Override
    public void retirar(double monto) {
        System.out.println("Retirando $" + monto);
    }
}

class ProxyCuentaBancaria implements CuentaBancaria {
    private CuentaBancariaReal cuentaReal = new CuentaBancariaReal();
    private int pinCorrecto;
    private int pinIngresado;

    public ProxyCuentaBancaria(int pinCorrecto, int pinIngresado) {
        this.pinCorrecto = pinCorrecto;
        this.pinIngresado = pinIngresado;
    }

    @Override
    public void retirar(double monto) {
        // Completar: comparar pines y actuar en consecuencia
    }
}
```

## Ejercicio 3
Completa `ProxyVideo`, que registra ("loggea") cada vez que se reproduce un video,
además de delegar la reproducción real.

```java
interface Video {
    void reproducir();
}

class VideoReal implements Video {
    private String titulo;

    public VideoReal(String titulo) {
        this.titulo = titulo;
    }

    @Override
    public void reproducir() {
        System.out.println("Reproduciendo: " + titulo);
    }
}

class ProxyVideo implements Video {
    private VideoReal videoReal;

    public ProxyVideo(String titulo) {
        this.videoReal = new VideoReal(titulo);
    }

    @Override
    public void reproducir() {
        // Completar: imprimir "Acceso registrado" y luego reproducir el video real
    }
}
```

## Ejercicio 4
Completa `ProxyApiExterna`, que cachea (guarda en memoria) el resultado de una consulta
costosa a `ApiExternaReal`, para no repetir la llamada si ya se consultó antes la misma clave.

```java
import java.util.HashMap;
import java.util.Map;

interface ApiExterna {
    String consultar(String clave);
}

class ApiExternaReal implements ApiExterna {
    @Override
    public String consultar(String clave) {
        System.out.println("Consultando API externa para: " + clave);
        return "Resultado de " + clave;
    }
}

class ProxyApiExterna implements ApiExterna {
    private ApiExternaReal apiReal = new ApiExternaReal();
    private Map<String, String> cache = new HashMap<>();

    @Override
    public String consultar(String clave) {
        // Completar: si la clave ya está en cache, devolverla sin llamar a apiReal;
        // si no, consultar, guardar en cache y devolver el resultado
    }
}
```

## Ejercicio 5
Completa `ProxyImpresora`, que limita la cantidad de páginas que un usuario puede
imprimir por día. Si supera el límite, imprime `"Límite de impresión alcanzado"`.

```java
interface Impresora {
    void imprimir(int paginas);
}

class ImpresoraReal implements Impresora {
    @Override
    public void imprimir(int paginas) {
        System.out.println("Imprimiendo " + paginas + " páginas");
    }
}

class ProxyImpresora implements Impresora {
    private ImpresoraReal impresoraReal = new ImpresoraReal();
    private int limiteDiario;
    private int impresasHoy = 0;

    public ProxyImpresora(int limiteDiario) {
        this.limiteDiario = limiteDiario;
    }

    @Override
    public void imprimir(int paginas) {
        // Completar: si impresasHoy + paginas supera el límite, denegar;
        // si no, imprimir, y acumular en impresasHoy
    }
}
```

## Ejercicio 6
Completa `ProxyRecursoRed`, que verifica la conexión a internet (simulada con un
`boolean conectado`) antes de permitir descargar un recurso.

```java
interface RecursoRed {
    void descargar(String url);
}

class RecursoRedReal implements RecursoRed {
    @Override
    public void descargar(String url) {
        System.out.println("Descargando desde: " + url);
    }
}

class ProxyRecursoRed implements RecursoRed {
    private RecursoRedReal recursoReal = new RecursoRedReal();
    private boolean conectado;

    public ProxyRecursoRed(boolean conectado) {
        this.conectado = conectado;
    }

    @Override
    public void descargar(String url) {
        // Completar: si no hay conexión, imprimir "Sin conexión a internet";
        // si hay, delegar la descarga
    }
}
```

## Ejercicio 7
Completa `ProxyDocumentoConfidencial`, similar al ejercicio de documentos visto en clase,
pero ahora controlando el acceso según el **departamento** del empleado (solo
"Legal" puede ver el documento). Si no pertenece a Legal, debe registrar el intento
fallido con `registrarIntentoFallido()`.

```java
interface Documento {
    void mostrar();
}

class DocumentoReal implements Documento {
    private String nombre;

    public DocumentoReal(String nombre) {
        this.nombre = nombre;
    }

    @Override
    public void mostrar() {
        System.out.println("Mostrando documento confidencial: " + nombre);
    }
}

class Empleado {
    private String nombre;
    private String departamento;

    public Empleado(String nombre, String departamento) {
        this.nombre = nombre;
        this.departamento = departamento;
    }

    public String getNombre() { return nombre; }
    public String getDepartamento() { return departamento; }
}

class ProxyDocumentoConfidencial implements Documento {
    private String nombre;
    private Empleado empleado;
    private DocumentoReal documentoReal;

    public ProxyDocumentoConfidencial(String nombre, Empleado empleado) {
        this.nombre = nombre;
        this.empleado = empleado;
    }

    @Override
    public void mostrar() {
        // Completar: si empleado.getDepartamento() es "Legal", crear (si hace falta)
        // y mostrar el documento real, imprimiendo "Acceso concedido a " + nombre del empleado;
        // si no, imprimir "Acceso denegado a " + nombre + " para el documento " + nombre del documento,
        // y llamar a registrarIntentoFallido()
    }

    public void registrarIntentoFallido() {
        // Completar: imprimir "Intento de acceso fallido registrado para " + nombre del empleado
    }
}
```
