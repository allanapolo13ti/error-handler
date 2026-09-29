# Levantar la solución — Error Handler

## 1. Prerequisitos

- Acceso a la instancia de **n8n** de Grupo Apolo (o un n8n local: `docker run -it --rm -p 5678:5678 n8nio/n8n`).
- Accesos a los sistemas externos que usa el proyecto (ver credenciales abajo). Solicitarlos a Brau (bdelsas@apolo.gt).

## 2. Credenciales a crear en n8n

Créalas en **n8n → Credentials → Add credential** antes de importar:

| Credencial | Tipo en n8n | La usan |
|---|---|---|
| Microsoft Teams OAuth2 | `microsoftTeamsOAuth2Api` | 🚨 Error Handler - Email & Teams |
| SMTP (envío de correos) | `smtp` | 🚨 Error Handler - Email & Teams |

> ⚠️ Nunca subas credenciales, tokens ni contraseñas a este repo. Los `workflow.json` se exportan sin secretos.

## 3. Importar los workflows

Después de publicarlo, asígnalo como **Error Workflow** en *Settings* de cada workflow que quieras monitorear.

Para cada carpeta dentro de `Codigo Fuente/`:

1. En n8n: **Workflows → Import from File** → selecciona su `workflow.json`.
2. Abre cada nodo marcado en rojo y asígnale la credencial correspondiente.
3. Revisa la sección *¿Cómo montarlo?* del `README.md` de esa carpeta (pasos extra por flujo).
4. Prueba con una ejecución manual y luego **publica / activa** el workflow.

## 4. Verificar

- En **Executions** confirma que la primera corrida termine en verde.
- Si algo falla, revisa *¿Qué revisar si falla?* en el README del flujo.
