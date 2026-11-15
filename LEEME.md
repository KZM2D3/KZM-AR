# KZM · Ticket AR · Odyssey

Experiencia de realidad aumentada del ticket KZM. Al escanear el QR de AR del reverso del ticket y apuntar la cámara a ese mismo lado, aparece el diorama animado de **Odyssey** (water coaster concept) encima del ticket.

**Link:** https://kzm2d3.github.io/KZM-AR/

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | La página de AR (MindAR + A-Frame). Cámara HD, materiales realistas, sombras y suavizado del movimiento. |
| `odyssey.glb` | El diorama animado: la zona de la atracción recortada de la escena de Blender, con los barcos en loop de 42 s. |
| `targets.mind` | El marcador que reconoce la cámara. Solo el reverso del ticket (lado del QR de AR), ignorando el nombre para no confundirlo con el frente. |
| `LEEME.md` | Este archivo. No lo usa la página. |

## Cómo actualizar

1. En el repo: **Add file > Upload files**, sube el archivo con el mismo nombre (lo reemplaza) y dale **Commit changes**.
2. Espera 1 o 2 minutos (pestaña **Actions**, palomita verde).
3. Pruébalo en pestaña privada. Si el celular muestra la versión vieja, agrega `?v=` y un número nuevo al final del link.

**No borres ni renombres el repo.** El QR de los tickets impresos apunta a este link.

## Ajustes rápidos (al inicio del código de `index.html`)

| Valor | Para qué sirve |
|---|---|
| `EXPOSURE = 0.85` | Brillo general. Súbelo a 1.0 si se ve oscuro; bájalo a 0.7 si se ve quemado. |
| `SCALE = 0.0052` | Tamaño del diorama. Con este valor cabe justo en el ticket. |
| `SMOOTH = 0.14` / `SMOOTH_ROT = 0.07` | Suavizado de posición y giro. Más bajo, más estable pero sigue más lento al ticket. |
| `DEAD_DEG = 0.8` / `DEAD_DIST = 0.012` | Zona muerta: movimientos más chicos se ignoran para que, quieto, no tiemble. |
| `JUMP_DEG = 25` / `JUMP_DIST = 0.35` | Saltos mayores a esto se ignoran salvo que se repitan varios frames (errores de detección). |
| `HOLD_MS = 700` | Cuánto se queda el diorama si la cámara pierde el ticket un momento. |
| `timeScale: 1` | Velocidad de la animación (2 = doble de rápido). |

## Importante

- **Si cambias el diseño del reverso del ticket**, hay que recompilar `targets.mind` con la imagen nueva. Si no, la cámara no lo reconoce.
- **Para usarlo bien:** buena luz sin reflejos, papel mate, el ticket ocupando unos dos tercios de la pantalla, y el Modo de bajo consumo apagado.
- Funciona en iPhone (Safari) y Android (Chrome). La cámara solo funciona por HTTPS, por eso vive en GitHub Pages.

## Impresión del ticket

- **Imprenta:** archivos de 3.66 × 2.16 in (corte 3.5 × 2 in, 0.08 in de sangrado por lado).
- **Kyocera ECOSYS (doble cara):** el reverso sale unos 4 mm más arriba, así que la hoja calibrada baja el reverso 4 mm. Misma bandeja, mismo papel y al 100%. Si cambia algo, imprime la hoja de prueba de 4 filas para recalibrar.
