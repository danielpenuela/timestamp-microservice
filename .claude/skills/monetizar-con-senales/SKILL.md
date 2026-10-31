---
name: monetizar-con-senales
description: "Cómo medir qué desean los usuarios y qué tan deseado es cada artículo o foto, elegir las mejores fotos, y vender en el momento correcto midiendo cuánto gana cada ofrecimiento, con límites de privacidad y sesgo. Inspirada en un análisis de Tinder. Cargar al diseñar recomendaciones, rankings, puntajes de fotos o productos, un modelo dentro de la app, pantallas de pago u ofertas, o al redactar promesas de privacidad sobre datos."
---

# Monetizar con señales

Lo atribuido a Tinder viene de un video que analiza la app descompilada y un conjunto de fotos
sintéticas propio. No está verificado; úsalo como inspiración, no como hecho.

## 1. Mide dos cosas

- **Qué quiere cada usuario.** El video dice que Tinder convierte en un *embedding* cada foto que
  le gusta a alguien y las promedia (`liked_swipees_image_average`), y que mide cuánto tiempo mira
  cada una.
- **Qué tan deseado es algo.** La proporción de quienes lo vieron y lo quisieron. Tinder la llama
  RSRR, *right swipe received ratio*.

**Aplícalo a artículos y fotos de productos, no a las personas:**
`deseo = veces que lo quisieron ÷ veces que lo vieron`. Exige un mínimo de vistas antes de confiar
en el número y guarda cuántas veces se mostró, para no premiar solo lo que ya estaba arriba.

## 2. Elige automáticamente las mejores fotos

La función de Tinder revisa hasta 20,000 fotos de los últimos 2 años y propone las 27 mejores. Tres
ideas se pueden copiar:

- Un modelo pequeño dentro del teléfono evita subir cada foto.
- Los límites son parámetros visibles y fáciles de ajustar, no números escondidos en el código.
- La persona recibe una propuesta y decide; la app no publica por su cuenta.

## 3. Audita antes de usar

El autor del video midió el modelo con imágenes iguales salvo un atributo. Haz lo mismo con cualquier
puntaje: pares que solo cambien en una cosa y compara la diferencia. Si cambia por rasgos de personas
o por algo ajeno al objetivo, por ejemplo el fondo de la foto, no está listo.

Según el video, el modelo daba más puntaje por ropa reveladora y menos por piel más oscura, y a las
mujeres por mayor peso o edad. Es el ejemplo de lo que hay que evitar.

## 4. Etiqueta cada ofrecimiento

En el video, cada venta lleva la marca de qué la provocó: `high_rsrr_upsell`. Copia esto: guarda en
cada oferta o pantalla de pago el **motivo** y el **lugar** donde se mostró, y súmalo al pago final.
Así se puede responder cuánto gana cada motivo y cuál conviene apagar. Compara con un grupo de control.

## 5. Que la promesa coincida con el código

El video contrasta el texto «todo se queda en tu dispositivo» con el envío de puntajes por foto.
Antes de publicar una promesa de privacidad, revisa cada campo que sale del teléfono. Si un puntaje
derivado sale, dilo; también es un dato. Actualiza la política de privacidad y las fichas de las tiendas.

## Límites que no se cruzan sin pedido expreso del dueño y revisión legal

- Nada de puntuar a las personas por cuerpo, piel, edad o atractivo.
- Nada de inferir datos sensibles a partir de fotos, ni de enviarlos a un servidor.
- Nada de cambiar el precio según lo que se calcule de una persona.
- Nada de esconder una venta detrás de información sobre otra persona: el video describe a quien le
  dio «me gusta» a un perfil popular llevándolo a una pantalla de pago.

## En este repo

Este repo es un ejercicio pequeño de API, sin producto ni usuarios: la skill queda aquí como referencia y no pide ningún cambio en él.

## Procedencia

Sacada el 2026-10-30 de un video corto enviado por el dueño del repo (transcrito y revisado
fotograma por fotograma). Los hechos sobre Tinder son afirmaciones del video, no comprobadas; la aplicación a artículos y los límites son decisiones añadidas aquí. No se incluye cómo descompilar apps ajenas. Última revisión: 2026-10-30.
