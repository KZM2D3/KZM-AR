# Tarjeta AR · Carrito Chaac (IRTRA)

Todo está listo para subir. La carpeta contiene:

| Archivo | Qué es |
|---|---|
| `index.html` | La experiencia AR |
| `model.glb` | El carrito optimizado, sin texturas (de 42 MB a 0.17 MB) |
| `targets.mind` | Los dos lados de la tarjeta compilados como marcadores |
| `tarjeta-frente.png`, `tarjeta-reverso.png` | Las imágenes usadas para compilar (referencia) |

Funciona con cualquiera de los dos lados de la tarjeta. El reverso (KZM + QR) rastrea mejor.

## Publicarlo (GitHub Pages, gratis)

La cámara solo funciona por HTTPS, así que no basta con abrir el archivo en la compu.

1. Crea un repo público en GitHub, por ejemplo `kzm-ar`.
2. Sube todos los archivos de esta carpeta (Add file > Upload files).
3. Settings > Pages > Source: Deploy from a branch > `main` / root > Save.
4. En un minuto queda en `https://TUUSUARIO.github.io/kzm-ar/`.
5. Ábrelo en el celular, acepta la cámara y apunta a la tarjeta (o a la imagen en tu pantalla).

## Ojo con el QR

Si cambias el QR del reverso para que apunte a esta página, el dibujo del reverso cambia, y `targets.mind` hay que volver a compilarlo con la tarjeta nueva. Compilador: https://hiukim.github.io/mind-ar-js-doc/tools/compile (sube primero el reverso y después el frente, en ese orden).

## Ajustes rápidos (al final de index.html)

- `SCALE = 0.15`: tamaño del carrito. La tarjeta mide 1 unidad de ancho.
- `SPIN = 14000`: milisegundos por vuelta. `0` lo deja quieto.
- `filterBeta` (arriba, en `a-scene`): si el carrito tiembla, bájalo; si se siente lento, súbelo.
- El botón "Ver portafolio" lleva a kzmdesigns.com.

## Materiales

El carrito va sin texturas, solo con los colores base de Cinema 4D (techo y caja azul, ruedas amarillas, lo demás blanco), con un look de maqueta. Si después quieres los materiales de tus renders, conviértelos a Standard/glTF en C4D (o hornea texturas) antes de exportar.
