🔐 Firewall Web Automation – n8n Workflow
📌 Descripción

Este workflow en n8n automatiza tareas operativas sobre un firewall o sistema web que no dispone de API oficial, replicando las solicitudes HTTP realizadas por la interfaz web.

El flujo:

Recibe datos vía Webhook

Normaliza los parámetros

Realiza autenticación contra el sistema web

Ejecuta una acción operativa (ej: crear regla, bloquear IP, etc.)

Devuelve respuesta estructurada

Este proyecto permite automatizar tareas repetitivas sin intervención manual.

🏗 Arquitectura del Flujo
Webhook → Edit Fields → Login → Execute Action

🔹 Webhook

Actúa como endpoint REST para recibir solicitudes externas.

🔹 Edit Fields

Normaliza y limpia los datos recibidos.

🔹 Login (HTTP Request)

Simula el inicio de sesión replicando la petición que realiza la interfaz web.

🔹 Execute Action (HTTP Request)

Ejecuta la acción deseada dentro del sistema (ej: bloqueo de IP, creación de regla).

📥 Entrada Esperada

El Webhook espera un POST con cuerpo JSON:

{
  "ip_fw": "192.168.1.1",
  "username": "admin",
  "password": "123456"
}


Se pueden agregar más parámetros dependiendo de la acción que se quiera automatizar.

🔄 Funcionamiento

El sistema externo o usuario envía una solicitud al webhook.

n8n recibe los datos.

Se procesan y normalizan los parámetros.

Se realiza autenticación en el sistema web.

Se ejecuta la acción solicitada.

Se devuelve una respuesta confirmando éxito o error.

🚀 Cómo Importar el Workflow

Abrir n8n

Ir a Workflows

Click en Import

Cargar el archivo .json del workflow

Configurar credenciales si aplica

Activar el workflow

🔐 Requisitos
