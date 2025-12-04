# Estudio Puente de Segovia — Informe de Entrega y Propuesta

## 1. Estado Actual del Proyecto (Entregado)
Se ha desarrollado una aplicación web a medida (no plantilla) optimizada para la conversión y la gestión automática de reglas de negocio.

### Tecnología y Funcionalidad
- **Web App Profesional**: Desarrollada en React + Vite + Tailwind. Carga instantánea y experiencia de usuario fluida ("app-like").
- **Sistema de Reservas Inteligente**:
  - Lógica de precios dinámica: Viernes (150€), Sábado (200€), Domingo (150€) y descuentos automáticos por packs de 2 o 3 días.
  - Validaciones de negocio: Bloqueo de días laborables, máximo 3 días por reserva, prevención de fechas pasadas.
- **Gestión de Solicitudes**: Sistema *Serverless* (sin servidor dedicado) para envío de emails transaccionales con resumen detallado de la reserva.
- **Internacionalización**: Web completamente bilingüe (Español/Inglés) con detección automática del idioma del usuario.

### Valor Diferencial
A diferencia de una web estándar (Wix/WordPress), esta solución ofrece:
- **Mantenimiento técnico bajo**: No hay bases de datos que mantener ni plugins que actualizar.
- **Escalabilidad**: Lista para crecer (pagos online, CRM) sin rehacer la base.
- **Seguridad**: Arquitectura moderna que minimiza vulnerabilidades.

---

## 2. Valoración Económica

### Proyecto Base (Estado Actual)
Desarrollo de la plataforma, lógica de negocio personalizada, integración de emails y diseño responsive.

**Inversión: 1.200 €**

### Ampliaciones Recomendadas (Fase 2)

#### Sistema de Gestión de Disponibilidad (Google Calendar)
Transforma la web en una herramienta de gestión automática.
- **Sincronización Bidireccional**: La web lee tu calendario y bloquea automáticamente las fechas ocupadas.
- **Automatización**: Al recibir una reserva, se crea el evento en tu calendario automáticamente.
- **Beneficio**: Elimina el riesgo de *overbooking* y te ahorra comprobar la agenda manualmente antes de cada confirmación.

**Inversión adicional: +500 €**

---

## 3. Plan de Mantenimiento y Soporte
Para asegurar el funcionamiento continuo y realizar actualizaciones.

**Opción A: Tranquilidad Total (Mensual)**
- Monitorización de disponibilidad (Uptime).
- Pequeños cambios de contenido (textos, fotos) hasta 1h/mes.
- Gestión de dominio y hosting.
- **Inversión: 50 - 90 € / mes**

**Opción B: Bolsa de Horas (Pago por uso)**
- Para cambios puntuales o nuevas funcionalidades bajo demanda.
- **Tarifa: 50 - 70 € / hora**

---

## Resumen de la Propuesta

| Concepto | Inversión | Impacto en el Negocio |
| :--- | :--- | :--- |
| **Web Base (Entregada)** | **1.200 €** | Presencia profesional y captación de leads cualificados. |
| **+ Automatización Calendar** | **+500 €** | Gestión de agenda automática y cero errores humanos. |
| **TOTAL PROYECTO** | **1.700 €** | Solución integral de reservas y gestión. |
