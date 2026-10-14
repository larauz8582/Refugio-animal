## 1. Diagrama de Casos de Uso

### Actores Principales
| Actor | Descripción |
|---|---|
| **Ciudadano / Reportante** | Reporta animales en situación de riesgo, indica ubicación y condición |
| **Voluntario** | Recibe el caso asignado, atiende al animal, registra avances y estado |
| **Veterinario** | Evalúa al animal, diagnostica enfermedades, prescribe y actualiza tratamientos |
| **Administrador del Refugio** | Valida reportes, asigna responsables, gestiona adopciones, cierra expedientes |

### Casos de Uso y Relaciones
- **Ciudadano**
  - Reportar animal rescatado
  - Consultar estado de su reporte

- **Administrador**
  - Validar expediente recibido
  - Asignar responsable (voluntario o veterinario)
  - Aprobar solicitud de adopción
  - Cerrar caso finalizado

- **Voluntario**
  - Atender animal asignado
  - Registrar novedades y avances
  - Actualizar estado del expediente

- **Veterinario**
  - Registrar evaluación médica
  - Emitir diagnóstico
  - Actualizar plan de tratamiento

---

## 2. Diagrama de Clases UML

### Clase Base: Usuario
### Clases Derivadas (Herencia)
### Clase Principal: Expediente
### Clases de Patrones de Diseño
---

## Resumen de Relaciones
- **Herencia:** `Administrador`, `Voluntario`, `Veterinario` → extienden a `Usuario`
- **Asociación:** `Expediente` ↔ `Usuario` (un expediente tiene un responsable)
- **Agregación:** `GestorNotificaciones` contiene lista de interesados
- **Dependencia:** `ExpedienteFactory` crea instancias de `Expediente`
Diagramas: Casos de Uso y Clases UML completados
