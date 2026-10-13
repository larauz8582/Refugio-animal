# Diagramas del Sistema de Gestión de Refugio Animal

## 1. Diagrama de Casos de Uso

### Actores
| Actor | Acciones |
|---|---|
| **Ciudadano** | Reportar animal, consultar estado del caso |
| **Administrador** | Validar expediente, asignar responsable, cerrar caso, aprobar adopción |
| **Voluntario** | Atender animal, registrar avances |
| **Veterinario** | Registrar diagnóstico, actualizar tratamiento |

### Relaciones
- Ciudadano → Reportar animal rescatado
- Administrador → Recibe el reporte → Valida → Asigna a Voluntario/Veterinario
- Voluntario/Veterinario → Actualiza estado → Administrador cierra el caso

## 2. Diagrama de Clases UML

### Clase Base
### Clases Hijas
### Clase Principal
### Clases de Patrones
- **ExpedienteFactory** → `crearExpediente(tipo): Expediente`
- **GestorNotificaciones** → `suscribir(Observador)`, `notificar(mensaje)`
- **ConexionBD** → `getInstancia(): ConexionBD` ← Única instancia
Diagramas: Casos de Uso y Clases UML completados
