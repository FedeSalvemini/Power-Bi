# 🇪🇸 🤖 Lead Gen B2B Automatizado (n8n Workflow)

**Objetivo de Negocio:** Extracción masiva, perfilado algorítmico y cualificación automática de leads comerciales (B2B) en múltiples zonas geográficas, filtrando negocios sin presencia digital sólida.

### ⚙️ Arquitectura del Flujo
![Arquitectura n8n](arquitectura.png)

### 🛠️ Nodos y Tecnologías Utilizadas
* **Manual Trigger:** Inicio controlado del proceso.
* **Set & SplitOut:** Configuración de queries dinámicas por categoría (ej. clínicas, estudios contables) y separación para procesamiento iterativo.
* **Google Places API (HTTP Request):** Consumo de API RESTful para extracción de datos de negocios (rating, teléfono, web, dirección) utilizando `X-Goog-Api-Key`.
* **Code (JavaScript):** Lógica avanzada de filtrado. Elimina negocios sin reseñas, descarta webs falsas/sociales (Instagram, Facebook), deduplica por URL de Maps y rankea el top 20 usando un score ponderado de calidad.
* **Google Sheets:** Ingesta de los leads limpios y formateados en una base de datos centralizada.

### 💡 Lógica de Implementación (JSON)
El código fuente del flujo se encuentra en el archivo `workflow.json` adjunto en este repositorio. Para auditarlo, puede importarse directamente en cualquier instancia local o cloud de n8n.

#### Resumen Técnico:
Pipeline de extracción y perfilado de prospectos B2B. A través de llamadas asíncronas a la API de Google Places, obtiene comercios locales y ejecuta un script de limpieza para descartar aquellos que no cumplen con los estándares de calidad definidos (falta de web, sin contacto, bajo rating), consolidando los "Hot Leads" en Google Sheets.

---

# 🇬🇧 🤖 Automated B2B Lead Gen (n8n Workflow)

**Business Objective:** Mass extraction, algorithmic profiling, and automatic qualification of B2B commercial leads across multiple geographic zones, filtering out businesses without a solid digital presence.

### ⚙️ Flow Architecture
![n8n Architecture](arquitectura.png)

### 🛠️ Nodes & Technologies Used
* **Manual Trigger:** Controlled process initiation.
* **Set & SplitOut:** Dynamic query configuration by category (e.g., clinics, accounting firms) and separation for iterative processing.
* **Google Places API (HTTP Request):** RESTful API consumption for business data extraction (rating, phone, web, address) using `X-Goog-Api-Key`.
* **Code (JavaScript):** Advanced filtering logic. Removes businesses without reviews, discards fake/social websites (Instagram, Facebook), deduplicates by Maps URL, and ranks the top 20 using a weighted quality score.
* **Google Sheets:** Ingestion of clean and formatted leads into a centralized database.

### 💡 Implementation Logic (JSON)
The source code of the flow is located in the attached `workflow.json` file in this repository. To audit it, it can be imported directly into any local or cloud n8n instance.

#### Technical Summary:
Extraction and B2B prospect profiling pipeline. Through asynchronous calls to the Google Places API, it fetches local businesses and executes a cleaning script to discard those that do not meet the defined quality standards (missing website, no contact info, low rating), consolidating the "Hot Leads" in Google Sheets.
