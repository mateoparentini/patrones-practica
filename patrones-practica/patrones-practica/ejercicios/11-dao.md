# Ejercicios — Patrón DAO (7 ejercicios — tema a reforzar)

## Ejercicio 1
Completa `LibroDAO` (usando una `List<Libro>` en memoria como "base de datos") con las
operaciones básicas de un DAO: guardar, buscar por id, listar todos y actualizar.

```java
import java.util.ArrayList;
import java.util.List;

class Libro {
    private int id;
    private String titulo;

    public Libro(int id, String titulo) {
        this.id = id;
        this.titulo = titulo;
    }

    public int getId() { return id; }
    public String getTitulo() { return titulo; }
    public void setTitulo(String titulo) { this.titulo = titulo; }
}

interface LibroDAO {
    void guardar(Libro libro);
    Libro buscarPorId(int id);
    List<Libro> listarTodos();
    void actualizar(Libro libro);
}

class LibroDAOImpl implements LibroDAO {
    private List<Libro> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Libro libro) {
        // Completar
    }

    @Override
    public Libro buscarPorId(int id) {
        // Completar: recorrer la lista y devolver el libro cuyo id coincida, o null
    }

    @Override
    public List<Libro> listarTodos() {
        // Completar
    }

    @Override
    public void actualizar(Libro libro) {
        // Completar: buscar el libro existente por id y actualizar su título
    }
}
```

## Ejercicio 2
Completa `ClienteDAO`, agregando también el método `eliminar(int id)`.

```java
import java.util.ArrayList;
import java.util.List;

class Cliente {
    private int id;
    private String nombre;
    private String email;

    public Cliente(int id, String nombre, String email) {
        this.id = id;
        this.nombre = nombre;
        this.email = email;
    }

    public int getId() { return id; }
    public String getNombre() { return nombre; }
    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }
}

interface ClienteDAO {
    void guardar(Cliente cliente);
    Cliente buscarPorId(int id);
    List<Cliente> listarTodos();
    void actualizar(Cliente cliente);
    void eliminar(int id);
}

class ClienteDAOImpl implements ClienteDAO {
    private List<Cliente> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Cliente cliente) {
        // Completar
    }

    @Override
    public Cliente buscarPorId(int id) {
        // Completar
    }

    @Override
    public List<Cliente> listarTodos() {
        // Completar
    }

    @Override
    public void actualizar(Cliente cliente) {
        // Completar
    }

    @Override
    public void eliminar(int id) {
        // Completar: eliminar de la lista el cliente con ese id
    }
}
```

## Ejercicio 3
Completa `PedidoDAO`, agregando un método adicional `listarPorCliente(int clienteId)`
que devuelva solo los pedidos de un cliente dado.

```java
import java.util.ArrayList;
import java.util.List;

class Pedido {
    private int id;
    private int clienteId;
    private double total;

    public Pedido(int id, int clienteId, double total) {
        this.id = id;
        this.clienteId = clienteId;
        this.total = total;
    }

    public int getId() { return id; }
    public int getClienteId() { return clienteId; }
    public double getTotal() { return total; }
}

interface PedidoDAO {
    void guardar(Pedido pedido);
    Pedido buscarPorId(int id);
    List<Pedido> listarTodos();
    List<Pedido> listarPorCliente(int clienteId);
}

class PedidoDAOImpl implements PedidoDAO {
    private List<Pedido> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Pedido pedido) {
        // Completar
    }

    @Override
    public Pedido buscarPorId(int id) {
        // Completar
    }

    @Override
    public List<Pedido> listarTodos() {
        // Completar
    }

    @Override
    public List<Pedido> listarPorCliente(int clienteId) {
        // Completar: devolver una nueva lista solo con los pedidos de ese cliente
    }
}
```

## Ejercicio 4
Completa `EstudianteDAO`, con el método `existe(int id)` que indica si ya hay un
estudiante guardado con ese id.

```java
import java.util.ArrayList;
import java.util.List;

class Estudiante {
    private int id;
    private String nombre;

    public Estudiante(int id, String nombre) {
        this.id = id;
        this.nombre = nombre;
    }

    public int getId() { return id; }
    public String getNombre() { return nombre; }
}

interface EstudianteDAO {
    void guardar(Estudiante estudiante);
    Estudiante buscarPorId(int id);
    List<Estudiante> listarTodos();
    boolean existe(int id);
}

class EstudianteDAOImpl implements EstudianteDAO {
    private List<Estudiante> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Estudiante estudiante) {
        // Completar
    }

    @Override
    public Estudiante buscarPorId(int id) {
        // Completar
    }

    @Override
    public List<Estudiante> listarTodos() {
        // Completar
    }

    @Override
    public boolean existe(int id) {
        // Completar: usar buscarPorId y verificar si no es null
    }
}
```

## Ejercicio 5
Completa `FacturaDAO`, con el método adicional `calcularTotalFacturado()` que suma el
monto de todas las facturas guardadas.

```java
import java.util.ArrayList;
import java.util.List;

class Factura {
    private int id;
    private double monto;

    public Factura(int id, double monto) {
        this.id = id;
        this.monto = monto;
    }

    public int getId() { return id; }
    public double getMonto() { return monto; }
}

interface FacturaDAO {
    void guardar(Factura factura);
    Factura buscarPorId(int id);
    List<Factura> listarTodos();
    double calcularTotalFacturado();
}

class FacturaDAOImpl implements FacturaDAO {
    private List<Factura> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Factura factura) {
        // Completar
    }

    @Override
    public Factura buscarPorId(int id) {
        // Completar
    }

    @Override
    public List<Factura> listarTodos() {
        // Completar
    }

    @Override
    public double calcularTotalFacturado() {
        // Completar: recorrer la lista y sumar los montos
    }
}
```

## Ejercicio 6
Completa `ReservaDAO`, con el método `cancelar(int id)` que elimina una reserva, y
`contarReservasActivas()` que devuelve cuántas reservas quedan.

```java
import java.util.ArrayList;
import java.util.List;

class Reserva {
    private int id;
    private String nombreCliente;

    public Reserva(int id, String nombreCliente) {
        this.id = id;
        this.nombreCliente = nombreCliente;
    }

    public int getId() { return id; }
    public String getNombreCliente() { return nombreCliente; }
}

interface ReservaDAO {
    void guardar(Reserva reserva);
    List<Reserva> listarTodos();
    void cancelar(int id);
    int contarReservasActivas();
}

class ReservaDAOImpl implements ReservaDAO {
    private List<Reserva> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Reserva reserva) {
        // Completar
    }

    @Override
    public List<Reserva> listarTodos() {
        // Completar
    }

    @Override
    public void cancelar(int id) {
        // Completar
    }

    @Override
    public int contarReservasActivas() {
        // Completar
    }
}
```

## Ejercicio 7
Completa `EmpleadoDAO`, con el método `actualizar(Empleado empleado)` que si el
empleado no existe, debe guardarlo como nuevo en lugar de fallar (upsert).

```java
import java.util.ArrayList;
import java.util.List;

class Empleado {
    private int id;
    private String nombre;
    private double salario;

    public Empleado(int id, String nombre, double salario) {
        this.id = id;
        this.nombre = nombre;
        this.salario = salario;
    }

    public int getId() { return id; }
    public String getNombre() { return nombre; }
    public double getSalario() { return salario; }
    public void setSalario(double salario) { this.salario = salario; }
}

interface EmpleadoDAO {
    void guardar(Empleado empleado);
    Empleado buscarPorId(int id);
    List<Empleado> listarTodos();
    void actualizar(Empleado empleado);
}

class EmpleadoDAOImpl implements EmpleadoDAO {
    private List<Empleado> baseDeDatos = new ArrayList<>();

    @Override
    public void guardar(Empleado empleado) {
        // Completar
    }

    @Override
    public Empleado buscarPorId(int id) {
        // Completar
    }

    @Override
    public List<Empleado> listarTodos() {
        // Completar
    }

    @Override
    public void actualizar(Empleado empleado) {
        // Completar: si existe, actualizar su salario; si no existe, guardarlo como nuevo
    }
}
```
