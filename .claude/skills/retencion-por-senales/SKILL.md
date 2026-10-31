---
name: retencion-por-senales
description: "Método para que los usuarios vuelvan a una app, inspirado en lo que un video atribuye a Duolingo: calcular a diario la probabilidad de que cada usuario regrese, con señales de uso, y avisar en el momento correcto con el motivo que le importa. Cargar al diseñar notificaciones, recordatorios, pantallas para reactivar permisos de avisos, métricas de abandono o de regreso, o cuando se pida que la gente vuelva a la app."
---

# Retención por señales

**La idea:** nada de esta atención es suerte. Se calcula un número por usuario, se actúa según ese
número y se elige bien el momento y el motivo.

Lo atribuido a Duolingo viene de un video que muestra código de la app descompilada. No está
verificado; úsalo como inspiración, no como hecho.

## 1. Un número diario por usuario

La probabilidad de que vuelva mañana. El video muestra `latest_tomorrow_prob` y
`previous_tomorrow_prob`: guardar el anterior permite ver si sube o baja.

Empieza con una fórmula simple y explicable. No hace falta un modelo hasta tener datos que lo justifiquen.

## 2. Las señales

| Señal | Ejemplo en el video | Qué sugiere |
| --- | --- | --- |
| Por dónde entró | `entry_point`: aviso, widget, atajo o ícono | Hábito propio frente a empujón |
| Cuánto hizo hoy | `num_sessions_completed_today` | Intensidad de uso |
| Cuánto falló | `num_challenges_incorrect` | Frustración |
| Si la app falló | `crashed_since_last_open` | Separa abandono por culpa nuestra |

Primero revisa qué de esto ya se registra. Usa solo eventos de la propia app.

## 3. El momento

El número solo sirve si llegas en el momento correcto. El video cuenta que Duolingo identifica redes
Wi-Fi con un resumen `SHA-256`, cuenta los días vistos en cada una (`daysSeen`) para saber si
probablemente estás en casa, y registra si el teléfono estaba en silencio (`ringer_mode`).

**Aquí no se copia eso.** Rastrear redes es invasivo y hay que declararlo y justificarlo ante las
tiendas y los usuarios. Sin pedido expreso del dueño y revisión legal, usa la alternativa:

- Aprende la hora local a la que cada usuario suele abrir la app y avisa cerca de esa hora.
- Mide cuántos avisos terminan en apertura, por tipo y por hora.

## 4. Pedir de nuevo los avisos

Si los apagó, no le pidas «activa las notificaciones». Dale el motivo que más le importa según lo
que ya se calculó. En el video son el progreso de un amigo, el puesto en la clasificación o su racha.

Ofrécelo una sola vez cada cierto tiempo y respeta el «no». Los avisos no pueden ser obligatorios,
y los de publicidad requieren permiso expreso según las reglas de App Store.

## Cómo saber si funciona

Deja un grupo de control sin el cambio y compara cuántos vuelven. Que suba el número de aperturas
por aviso no demuestra nada si esas personas iban a volver igual. Vigila también cuántos apagan los
avisos o desinstalan.

## Límites

- Lo urgente de verdad, como pagos o transacciones, no se retrasa por este cálculo.
- No uses presión falsa: ni rachas inventadas, ni plazos que no existen.
- Declara en la política de privacidad y en las fichas de las tiendas todo dato nuevo que se recoja.

## En este repo

Este repo es un ejercicio pequeño de API, sin producto ni usuarios: la skill queda aquí como referencia y no pide ningún cambio en él.

## Procedencia

Sacada el 2026-10-30 de un video corto enviado por el dueño del repo (transcrito y revisado
fotograma por fotograma). Las secciones 1 a 4 resumen el video; la alternativa a Wi-Fi, el grupo de control y los límites son decisiones añadidas aquí. Última revisión: 2026-10-30.
