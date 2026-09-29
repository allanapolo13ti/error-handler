# 🚨 Error Handler - Email & Teams

| ID | Estado | Nodos | Creado | Actualizado |
|---|---|---|---|---|
| `eDCgfMVZmW4xTA5B` | 🟢 Activo | 7 | 2026-02-17 | 2026-03-03 |

## ¿Qué hace?

Workflow central de alertas: cuando otro workflow falla, envía el detalle por correo y lo publica en Teams (con alerta urgente si la severidad es alta).

## Trigger

- Error Trigger (se ejecuta cuando otro workflow falla)

## ¿Cómo funciona?

1. Se dispara automáticamente cuando falla un workflow que lo tenga configurado como *Error Workflow*.
2. Formatea el error (workflow, nodo, mensaje, severidad).
3. Envía correo y mensaje al canal de Teams.
4. Si la severidad es ALTA, manda además una alerta urgente a Teams.

## Dependencias

Correo (SMTP) · Microsoft Teams

## Credenciales a configurar

- Correo (SMTP)
- Microsoft Teams

## ¿Cómo montarlo?

1. En n8n: **Import from File** → seleccionar `workflow.json` de esta carpeta.
2. Configurar las credenciales de los servicios listados arriba.
3. Probar con una ejecución manual y luego **publicar**.

**Además, para este workflow:**

- Credencial SMTP y credencial de Microsoft Teams (canal Ciberseguridad).
- En cada workflow a vigilar: *Settings → Error Workflow →* seleccionar este.
- Debe estar publicado; solo aplica a ejecuciones de producción (no pruebas manuales).

## Si falla

- Abrir el workflow en n8n → **Executions** → la ejecución en rojo muestra el nodo que falló y el mensaje de error.
- **No llegan alertas:** el workflow que falló no lo tiene como Error Workflow, o el fallo fue en una prueba manual.
- **Error de Teams:** el token de Teams expiró o cambió el canal.

