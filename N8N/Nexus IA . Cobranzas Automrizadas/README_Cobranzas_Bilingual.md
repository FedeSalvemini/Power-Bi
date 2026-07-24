# 🇪🇸 🤖 Gestor de Cobranzas (Dunning System) (n8n Workflow)

**Objetivo de Negocio:** Automatización del proceso de cuentas por cobrar. Notificación proactiva y multicanal a clientes según el estatus de vencimiento de sus facturas para reducir los días de mora.

### ⚙️ Arquitectura del Flujo
![Arquitectura n8n](arquitectura.png)

### 🛠️ Nodos y Tecnologías Utilizadas
* **Schedule Trigger:** Orquestación temporal diaria (Ej. 9:00 AM).
* **Google Sheets (Read/Update):** Extracción del maestro de deuda y actualización del estado de gestión ("Marcar como avisado").
* **Code (JavaScript):** Motor de reglas de negocio que calcula los días de desfasaje contra el vencimiento (mora, vence hoy, prevención) y redacta mensajes personalizados y dinámicos para cada escenario.
* **Telegram / Meta WhatsApp API (HTTP Request):** Múltiples canales de salida para notificar al cliente el estado de su deuda y enviar el link de pago.

### 💡 Lógica de Implementación (JSON)
El código fuente del flujo se encuentra en el archivo `workflow.json` adjunto en este repositorio. Para auditarlo, puede importarse directamente en cualquier instancia local o cloud de n8n.

#### Resumen Técnico:
Sistema de *Dunning* (Gestión de Cobranzas). Monitorea diariamente una base de cuentas por cobrar, calcula la situación crediticia de cada cliente en tiempo real y detona notificaciones multicanal (Telegram/WhatsApp) con links de pago, segmentando el tono del mensaje según la urgencia (prevención vs. mora).

---

# 🇬🇧 🤖 Automated Collections (Dunning System) (n8n Workflow)

**Business Objective:** Accounts receivable process automation. Proactive and multichannel notification to clients based on the expiration status of their invoices to reduce days in arrears.

### ⚙️ Flow Architecture
![n8n Architecture](arquitectura.png)

### 🛠️ Nodes & Technologies Used
* **Schedule Trigger:** Daily temporal orchestration (e.g., 9:00 AM).
* **Google Sheets (Read/Update):** Extraction of the debt master data and update of the management status ("Mark as notified").
* **Code (JavaScript):** Business rules engine that calculates the offset days against the due date (overdue, due today, prevention) and drafts personalized and dynamic messages for each scenario.
* **Telegram / Meta WhatsApp API (HTTP Request):** Multiple output channels to notify the client of their debt status and send the payment link.

### 💡 Implementation Logic (JSON)
The source code of the flow is located in the attached `workflow.json` file in this repository. To audit it, it can be imported directly into any local or cloud n8n instance.

#### Technical Summary:
Dunning System (Automated Collections). Daily monitoring of an accounts receivable database, calculates the credit situation of each client in real time, and triggers multichannel notifications (Telegram/WhatsApp) with payment links, segmenting the tone of the message according to urgency (prevention vs. overdue).
