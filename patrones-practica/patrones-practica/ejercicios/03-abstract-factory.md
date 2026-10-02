# Ejercicios — Patrón Abstract Factory

## Ejercicio 1
Fábrica de componentes de interfaz según el sistema operativo.

* `Boton` y `Checkbox`: interfaces, cada una con un método `renderizar()`.
* `BotonWindows`, `BotonMac`, `CheckboxWindows`, `CheckboxMac`: implementaciones concretas.
* `UIFactory`: interfaz con `crearBoton()` y `crearCheckbox()`.
* `WindowsFactory` y `MacFactory`: implementaciones concretas de la fábrica.

```java
interface Boton {
    void renderizar();
}
interface Checkbox {
    void renderizar();
}

class BotonWindows implements Boton {
    @Override
    public void renderizar() { System.out.println("Botón estilo Windows"); }
}
class BotonMac implements Boton {
    @Override
    public void renderizar() { System.out.println("Botón estilo Mac"); }
}
class CheckboxWindows implements Checkbox {
    @Override
    public void renderizar() { System.out.println("Checkbox estilo Windows"); }
}
class CheckboxMac implements Checkbox {
    @Override
    public void renderizar() { System.out.println("Checkbox estilo Mac"); }
}

interface UIFactory {
    // Completar: declarar los dos métodos de creación
}

class WindowsFactory implements UIFactory {
    // Completar
}

class MacFactory implements UIFactory {
    // Completar
}
```

## Ejercicio 2
Fábrica de muebles según el estilo (Moderno / Clásico).

* `Silla` y `Mesa`: interfaces con método `describir()`.
* `SillaModerna`, `MesaModerna`, `SillaClasica`, `MesaClasica`: implementaciones.
* `MuebleFactory`: interfaz con `crearSilla()` y `crearMesa()`.
* `ModernoFactory` y `ClasicoFactory`: implementaciones concretas.

```java
interface Silla {
    void describir();
}
interface Mesa {
    void describir();
}

class SillaModerna implements Silla {
    @Override
    public void describir() { System.out.println("Silla de diseño moderno"); }
}
class MesaModerna implements Mesa {
    @Override
    public void describir() { System.out.println("Mesa de diseño moderno"); }
}
class SillaClasica implements Silla {
    @Override
    public void describir() { System.out.println("Silla de estilo clásico"); }
}
class MesaClasica implements Mesa {
    @Override
    public void describir() { System.out.println("Mesa de estilo clásico"); }
}

interface MuebleFactory {
    // Completar
}

class ModernoFactory implements MuebleFactory {
    // Completar
}

class ClasicoFactory implements MuebleFactory {
    // Completar
}
```

## Ejercicio 3
Fábrica de ingredientes para pizzas (Vegetariana / Carnívora).

* `Base` y `Topping`: interfaces con método `agregar()`.
* `BaseVegetariana`, `ToppingVegetariano`, `BaseCarnivora`, `ToppingCarnivoro`: implementaciones.
* `PizzaFactory`: interfaz con `crearBase()` y `crearTopping()`.
* `VegetarianaFactory` y `CarnivoraFactory`: implementaciones concretas.

```java
interface Base {
    void agregar();
}
interface Topping {
    void agregar();
}

class BaseVegetariana implements Base {
    @Override
    public void agregar() { System.out.println("Base integral"); }
}
class ToppingVegetariano implements Topping {
    @Override
    public void agregar() { System.out.println("Verduras y queso"); }
}
class BaseCarnivora implements Base {
    @Override
    public void agregar() { System.out.println("Base clásica"); }
}
class ToppingCarnivoro implements Topping {
    @Override
    public void agregar() { System.out.println("Carnes variadas"); }
}

interface PizzaFactory {
    // Completar
}

class VegetarianaFactory implements PizzaFactory {
    // Completar
}

class CarnivoraFactory implements PizzaFactory {
    // Completar
}
```

## Ejercicio 4
Fábrica de uniformes deportivos según el equipo (Local / Visitante).

* `Camiseta` y `Short`: interfaces con método `mostrarColor()`.
* `CamisetaLocal`, `ShortLocal`, `CamisetaVisitante`, `ShortVisitante`: implementaciones.
* `UniformeFactory`: interfaz con `crearCamiseta()` y `crearShort()`.
* `LocalFactory` y `VisitanteFactory`: implementaciones concretas.

```java
interface Camiseta {
    void mostrarColor();
}
interface Short {
    void mostrarColor();
}

class CamisetaLocal implements Camiseta {
    @Override
    public void mostrarColor() { System.out.println("Camiseta azul (local)"); }
}
class ShortLocal implements Short {
    @Override
    public void mostrarColor() { System.out.println("Short azul (local)"); }
}
class CamisetaVisitante implements Camiseta {
    @Override
    public void mostrarColor() { System.out.println("Camiseta blanca (visitante)"); }
}
class ShortVisitante implements Short {
    @Override
    public void mostrarColor() { System.out.println("Short blanco (visitante)"); }
}

interface UniformeFactory {
    // Completar
}

class LocalFactory implements UniformeFactory {
    // Completar
}

class VisitanteFactory implements UniformeFactory {
    // Completar
}
```

## Ejercicio 5
Fábrica de componentes de base de datos (MySQL / MongoDB).

* `Conexion` y `Consulta`: interfaces con método `ejecutar()`.
* `ConexionMySQL`, `ConsultaMySQL`, `ConexionMongo`, `ConsultaMongo`: implementaciones.
* `BaseDatosFactory`: interfaz con `crearConexion()` y `crearConsulta()`.
* `MySQLFactory` y `MongoFactory`: implementaciones concretas.

```java
interface Conexion {
    void ejecutar();
}
interface Consulta {
    void ejecutar();
}

class ConexionMySQL implements Conexion {
    @Override
    public void ejecutar() { System.out.println("Conectando a MySQL"); }
}
class ConsultaMySQL implements Consulta {
    @Override
    public void ejecutar() { System.out.println("Ejecutando consulta SQL"); }
}
class ConexionMongo implements Conexion {
    @Override
    public void ejecutar() { System.out.println("Conectando a MongoDB"); }
}
class ConsultaMongo implements Consulta {
    @Override
    public void ejecutar() { System.out.println("Ejecutando consulta NoSQL"); }
}

interface BaseDatosFactory {
    // Completar
}

class MySQLFactory implements BaseDatosFactory {
    // Completar
}

class MongoFactory implements BaseDatosFactory {
    // Completar
}
```
