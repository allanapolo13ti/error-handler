# Error Handler

Manejador global de errores de n8n: avisa por correo y Teams cuando un workflow falla.

| Stack | Estado |
|---|---|
| n8n · SMTP · Teams | 🟢 Activo |

## Workflows

| Workflow | Carpeta | Trigger |
|---|---|---|
| [🚨 Error Handler - Email & Teams](<Codigo Fuente/error-handler-email-teams/>) | `error-handler-email-teams` | errorTrigger |

Cada carpeta trae su `workflow.json` (listo para importar, **sin credenciales**) y un `README.md` con qué hace, cómo funciona y qué revisar si falla.

## Estructura

```
error-handler/
├── BD/                    # Scripts de base de datos (n/a: flujos n8n)
├── Codigo Fuente/         # Workflows de n8n (workflow.json + README por flujo)
└── LEVANTAR_SOLUCION.md   # Cómo montarlo desde cero
```

→ **[Cómo levantar la solución](LEVANTAR_SOLUCION.md)**

---

Parte del [Dev Hub de Grupo Apolo](https://github.com/GrupoApolo/dev-hub).
