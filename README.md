# Jarvis Copilot

Un copiloto de voz para auto de rideshare: saluda a los pasajeros, conversa con
ellos y responde a comandos del conductor (chiste, pregunta, despedida).
Pensado para correr en un iPad montado en el auto.

## Puesta en marcha

1. **Activar GitHub Pages** (una sola vez): en este repo, ir a
   `Settings → Pages → Build and deployment → Source: Deploy from a branch`,
   elegir rama `main` y carpeta `/ (root)`, guardar. GitHub te va a dar una
   URL del tipo `https://manchino21.github.io/jarvis-copilot/` (puede tardar
   1-2 minutos la primera vez).
2. **Conseguir una clave de API de Anthropic**: entrá a
   [console.anthropic.com](https://console.anthropic.com/settings/keys),
   creá una cuenta si no tenés, y generá una API key. Es de pago por uso
   (no la suscripción de Claude.ai), pero cada charla cuesta centavos con el
   modelo que usa esta app (Haiku).
3. **Abrir la página en el iPad**, en Safari. Tocá el ⚙ arriba a la derecha,
   pegá tu clave de API y guardá. Quedá guardada solo en ese navegador
   (localStorage), nunca se sube a ningún lado más que a la API de Anthropic.
4. Tocá **Saludar** cuando suba un pasajero. Dale permiso al micrófono la
   primera vez que lo pida Safari.
5. (Opcional) En Safari, `Compartir → Agregar a pantalla de inicio` para que
   quede como un ícono de app en el iPad.

## Cómo funciona

- `index.html` / `jarvis.js`: toda la app es un sitio estático, sin backend.
- Reconocimiento y síntesis de voz: Web Speech API del navegador (nativo de
  Safari/iOS).
- El "cerebro" de Jarvis: llamadas directas a la API de Anthropic
  (`claude-haiku-5-5`) desde el navegador, con la clave que guardaste en ⚙.
- Si la voz suena robótica, instalá una voz "mejorada/premium" en
  `Ajustes del iPad → Accesibilidad → Contenido hablado → Voces` — van a
  aparecer en el selector de voz de Jarvis.

## Seguridad de la clave de API

La clave vive solo en el `localStorage` de tu navegador en el iPad. No está
en el código ni en este repo. Si alguna vez querés invalidarla, hacelo desde
console.anthropic.com.
