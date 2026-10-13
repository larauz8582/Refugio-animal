# Patrones de Diseño Aplicados

---

## Patrón 1: Singleton — Conexión a Base de Datos

### Propósito
Garantizar que exista **una única instancia** de la conexión a la base de datos en todo el sistema, evitando conexiones duplicadas y consumo innecesario de recursos.

### Problema que resuelve
Si cada módulo abre su propia conexión, se desperdician recursos y puede haber conflictos. Con Singleton, todos usan la misma conexión.

### Aplicación en el proyecto
- Clase: `ConexionBD`
- Método principal: `getInstancia()` → siempre devuelve la misma instancia
- Uso: Expediente, Usuarios y Notificaciones comparten la conexión

---

## Patrón 2: Factory Method — Creación de Expedientes

### Propósito
Crear objetos de tipo `Expediente` **sin especificar la clase concreta**, permitiendo agregar nuevas especies sin modificar el código existente.

### Problema que resuelve
Cada especie tiene campos y reglas distintas (Perro, Gato, Fauna Silvestre). Si usamos `new` directamente, el código se vuelve rígido y difícil de ampliar.

### Aplicación en el proyecto
- Clase: `ExpedienteFactory`
- Método: `crearExpediente(tipoEspecie)`
- Devuelve el objeto adecuado según el tipo:
  - `"PERRO"` → `ExpedientePerro`
  - `"GATO"` → `ExpedienteGato`
  - `"FAUNA"` → `ExpedienteFauna`
- ✅ Cumplimiento de Requerimiento: **Escalabilidad**

---

## Patrón 3: Observer — Notificaciones Automáticas

### Propósito
Cuando cambia el estado de un expediente, **se avisa automáticamente** a todos los interesados (responsable, administrador) sin que el sistema principal sepa quiénes son.

### Problema que resuelve
Si el código de notificación se escribe directamente dentro de la clase Expediente, cada vez que se agregue un nuevo medio de aviso, habría que modificar el código base.

### Aplicación en el proyecto
- Sujeto: `Expediente` → cuando cambia de estado, avisa a todos
- Observadores: `Voluntario`, `Administrador`, `SistemaCorreo`
- Métodos clave:
  - `suscribir(Observador)` → agrega interesados
  - `desuscribir(Observador)` → retira interesados
  - `notificar(mensaje)` → avisa a todos simultáneamente
- ✅ El sistema se mantiene limpio y fácil de ampliar

---

## Resumen

| Patrón | Principio | Beneficio |
|---|---|---|
| **Singleton** | Única instancia | Eficiencia en recursos |
| **Factory** | Extensible sin modificar | Agregar nuevas especies fácilmente |
| **Observer** | Desacoplamiento | Notificaciones sin afectar el código central |
Patrones: Singleton, Factory y Observer documentados
