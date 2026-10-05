# Mind — Landing

Página de presentación de Mind, soporte clínico para psicólogos. Es un único `index.html` estático: HTML, CSS y JS vanilla en un solo archivo, sin build ni dependencias.

## Ver en local

Cualquier servidor estático sirve, por ejemplo:

```bash
python -m http.server 4321
```

Después abrí `http://localhost:4321`. Abrir el archivo con doble clic también funciona, salvo las fuentes si no hay conexión.

## Desplegar

Se sube `index.html` tal cual, sin build:

- **Netlify:** arrastrar la carpeta a app.netlify.com/drop, o conectar el repo con "publish directory" en la raíz.
- **Vercel / Cloudflare Pages:** proyecto estático, sin comando de build, directorio de salida `.`.
- **GitHub Pages:** Settings → Pages → rama `main`, carpeta `/ (root)`.

## Qué incluye

- **Tema claro y oscuro:** respeta el del sistema y recuerda la elección del visitante en `localStorage`, con la clave `mind-theme`, la misma que la app.
- **Animaciones:** entrada del hero, flotación, formas que respiran y animaciones ligadas al scroll (`animation-timeline: view()`). Firefox usa un fallback con `IntersectionObserver`. Con "reducir movimiento" activado, todo queda estático.
- **Interacciones:** explorador de funcionalidades, carrusel de teléfonos en mobile, demo de privacidad, "Ver original de Mindy" y preguntas frecuentes.
- **Fechas de los mockups:** se calculan desde el día actual, así la página no envejece.
- **Logos y fuentes:** los logos van embebidos. Las fuentes (Fraunces y Plus Jakarta Sans) se cargan desde Google Fonts.

## Editar

- **Textos:** se cambian directamente en el HTML.
- **Estilos:** el CSS del `<style>` es Tailwind ya compilado con los tokens de Mind (`--mind-*`, en `:root` y `.dark`). Solo existen las clases que la página ya usa. Para una clase nueva hay dos caminos:
  - agregar CSS propio al final del `<style>`, usando los tokens (`rgb(var(--mind-wine))`);
  - recompilar con Tailwind CLI usando el preset de tokens de Mind.
- **Animaciones y medidas de los mockups:** están en la parte del CSS bajo "Animaciones y medidas de la landing".
- **Comportamiento:** el JS está al final del archivo, comentado por sección.

## Pendientes antes de publicar

- **Botones de cuenta:** "Crear cuenta" e "Iniciar sesión" están ocultos a propósito, porque la app todavía no está publicada. Cuando lo esté, hay que volver a agregarlos en el header, el hero y el CTA final, apuntando a la app.
- **Línea de emergencia del footer:** está configurada como 0800-345-1435, la línea nacional del Centro de Asistencia al Suicida. Verificá que siga vigente.
- **Links del footer:** Términos, Privacidad y Contacto no están incluidos, porque todavía no hay páginas públicas para esos destinos.
