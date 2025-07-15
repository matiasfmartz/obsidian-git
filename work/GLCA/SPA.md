# 🧱 SPA - Galicia - Standalone Deployment
---
### 1. 🔁 Migrar a `brick-spa-starter-kit` (recomendado)

- Es un repositorio base oficial del banco. [[Links utiles#^41e9d4]]
- Viene preconfigurado con:
  - Normas de seguridad.
  - Arquitectura del banco.
  - Tipado en **TypeScript**.
  - Configuración lista para el **entorno de OCP4**.
- Apto para SPA **standalone** o **embebida**.
- Soportado oficialmente por los equipos internos.

---

## 🛠️ Pasos para crear una SPA Standalone con `brick-spa-starter-kit`

### 🧱 Requisitos previos

- Repositorio basado en `brick-spa-starter-kit`.
- Archivos en **TypeScript** (`.ts`, `.tsx`).
- Node.js y npm configurados en entorno Galicia.

### 🔧 Configurar build como **standalone**

Modificar el `package.json`:



Este script:
- Compila los widgets si los hay
- Realiza el build de Next.js
- Exporta como SPA lista para deploy.

🧭 Consideraciones de despliegue
🔒 ¿Dónde se despliega?

✅ Interno (red Galicia) → OCP en un container.
❌ Externo (ofb/onb) → Usa widgets, requiere otro enfoque (no cubierto en esta nota).

🧱 Brick está preparado por defecto para:
- SPA embebida.
- Pero se puede transformar en standalone con los cambios mencionados.

🧵 Otros detalles: 

- Tipo de proyecto: Next.js con TypeScript.
- El starter incluye estructuras y dependencias necesarias para evitar errores comunes.
- La migración al brick-spa-starter-kit es la opción con mayor mantenibilidad y soporte.


📎 Recursos

Brick SPA Starter Kit
gcba-spa build-widgets
OCP Galicia Deploy
Widgets OFB/ONB Galicia