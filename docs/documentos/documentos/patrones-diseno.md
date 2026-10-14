# Patrones de Diseño Aplicados

---

## Patrón 1: Singleton — Conexión a Base de Datos

### Propósito
Garantizar que en todo el sistema exista **una única instancia** de la conexión a la base de datos, evitando abrir conexiones repetidas que consumen recursos innecesarios.

### Problema que resuelve
Si cada clase o módulo abre su propia conexión a la base de datos, se generan conflictos, se desperdician recursos y el sistema se vuelve lento e inestable. Con Singleton, todos los componentes comparten la misma conexión.

### Estructura

### Aplicación en el proyecto
- Cuando cualquier módulo necesita acceder a datos (guardar expediente, consultar usuario), llama a `ConexionBD.getInstancia()`
- Si la conexión **no existe aún**, se crea la primera y única
- Si **ya existe**, se devuelve la misma instancia
- ✅ Beneficio: Eficiencia, control centralizado, sin duplicados

---

## Patrón 2: Factory Method — Creación de Expedientes

### Propósito
Crear objetos de tipo `Expediente` **sin indicar directamente la clase concreta**, permitiendo agregar nuevas especies o tipos de expediente **sin modificar el código existente**.

### Problema que resuelve
Si usamos `new ExpedientePerro()`, `new ExpedienteGato()` directamente en el código principal, cada vez que se agregue una nueva especie habrá que modificar muchas partes del sistema. El código se vuelve rígido y difícil de mantener.

### Estructura
Sujeto → Expediente
- listaObservadores: List
------------------------
+ suscribir(Observador)
+ desuscribir(Observador)
+ notificarCambio(mensaje)

Observador (interfaz)
------------------------
+ actualizar(mensaje, expediente)

Observadores concretos:
  → Administrador, Voluntario, SistemaCorreo
  


