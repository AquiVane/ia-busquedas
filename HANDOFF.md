# HANDOFF — ia-busquedas (IA Búsquedas)

*Creado: 11/10/2026.*

## Qué es
App independiente de monitor de presencia de marca en búsquedas de IA: pocas preguntas por marca, consultadas una vez por semana, con reporte simple (¿te nombró la IA? ¿en qué lugar? ¿a quién nombró en cambio?). Se suma también como bloque al reporte mensual de los clientes de COSMART.

## Estado
Repo recién creado, vacío de código. Decisiones tomadas en la sesión "Aplicaciones sin hacer para vender" (11/10):
- Las herramientas existentes (Ahrefs Brand Radar desde USD 50/mes, hasta 699) son caras; la idea es una versión mínima y barata para pymes en español.
- Restricción: solo gratis. Consultar a ChatGPT/Perplexity por API tiene costo; hay que buscar cuotas gratuitas reales antes de decidir.

## Pendiente real
1. Relevar qué servicios de IA tienen cuota gratis real y sus límites (traerle el detalle a Vaneh; NO conectar nada sin su autorización).
2. Landing + login propio.
3. Fase 3 del plan: se construye después del Play y de App de Cobro.

## Reglas duras
- Vaneh se comunica **solo en español** (rioplatense) — nunca respondas en inglés.
- **Nunca hagas cambios no pedidos.** Si algo parece mejorable, preguntá antes.
- **Solo servicios GRATUITOS.** Nada con costo fijo para COSMART (decisión de Vaneh, 11/10). Antes de usar cualquier servicio externo, verificar que sea gratis y avisar si tiene un límite que pueda empezar a cobrar. Sin tarjetas ni planes pagos hasta que haya ingresos y ella lo autorice.
- **Cada app es independiente**: propia landing, propio login, propios usuarios y contraseñas. Quien compra una NO accede al Hub ni a las otras apps.
- **Sin WhatsApp** por ahora (decisión de Vaneh): los avisos van por mail.
- **Texto primero**: todo texto que haya que escribir (mails, copys, explicaciones) se muestra en el chat y se espera aprobación antes de seguir.
- **Landings / páginas nuevas**: primero preview en artifact para que Vaneh corrija ahí mismo. Responsive mobile primero. Texto claro sobre fondos oscuros. Revisar que todos los botones funcionen.
- **Branding COSMART** (para el uso interno y los clientes de COSMART): brújula/viajeros/destinos; Playfair Display + DM Sans; colores `#0D2B6B` `#1A4DAA` `#3A8FC7` `#E02020` `#F2EDE6`. Ver `cosmart-workers/clientes/cosmart/AI_OPERATING_SYSTEM.md`. Para el resto de los clientes de las apps, textos neutros.
- **Cron triggers de Cloudflare: la cuenta está al tope (5/5, Workers Free).** No agregar crons nuevos; reusar uno existente de `cosmart-workers` o consultar a Vaneh. Deploy de workers siempre MANUAL y avisando antes.
- **Rendimiento (que no se rompa al crecer)**: datos en filas chicas e indexadas (D1), nunca bloques JSON gigantes; listas paginadas; carga por partes; envíos de mail en cola con tope diario; topes de clientes por plan; prueba de carga antes de lanzar; medir velocidad antes de sumar funciones.
- **Precios de lanzamiento**: Inicial USD 3/mes (hasta 20 clientes) · Plus USD 5/mes (hasta 50) · Pro USD 8/mes (hasta 150). Anual: pagás 10 meses, usás 12 (USD 30 / 50 / 80). Los 2 meses gratis aplican SOLO al plan anual pagado por adelantado; NO hay meses gratis al inicio. Prueba gratis solo para clientes actuales de COSMART.
