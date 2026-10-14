# Mouse FPV — Exploración 3D

Juego web en primera persona con Three.js, pensado para Chromebook y controles de puntero facial.

## Jugar
Abre la página publicada en GitHub Pages. Para desarrollo local, sirve la carpeta con un servidor HTTP (por ejemplo, `python -m http.server 8000`) y abre `http://localhost:8000`.

## Controles
- **Mirada:** mueve el puntero facial para girar la cámara.
- **WASD** o flechas: moverte por el mundo.
- **Botones de flechas en pantalla:** movimiento accesible con cursor, pantalla táctil o ratón.
- **Shift** o botón «Correr»: caminar más rápido.
- **Volver al inicio:** restablece la posición y la mirada.
- **Pantalla completa:** amplía la vista.

## Modelo LowPolyCity
El juego ya está configurado para cargar `./models/LowPolyCity.glb` delante del punto inicial. Para incluir el archivo del modelo en el repositorio, descomprime el paquete que se preparó y sube `models/LowPolyCity.glb` a la carpeta `models/` de GitHub. El GLB contiene las texturas integradas, por lo que no necesitas los PNG separados del ZIP original.

## Añadir más modelos 3D propios
1. Exporta el modelo como **GLB** (recomendado) o glTF.
2. Sube el archivo a la carpeta `models/`. En GLB, las texturas suelen ir dentro del mismo archivo.
3. Añade una entrada en el arreglo `MODEL_URLS` de `index.html`. Ejemplo:

```js
const MODEL_URLS = [
  { url: './models/LowPolyCity.glb', position: [0, 0, -8], scale: 1, rotationY: 0 },
  { url: './models/casa.glb', position: [8, 0, -12], scale: 1, rotationY: 0 }
];
```

- `position`: ubicación `[x, y, z]`; el suelo está en `y = 0`.
- `scale`: tamaño del modelo; empieza con `1`.
- `rotationY`: giro horizontal en radianes.
- Si tu modelo es glTF con archivos de textura externos, conserva la estructura de carpetas y rutas relativas.

**Importante:** los nombres y rutas deben coincidir exactamente, incluyendo mayúsculas y minúsculas. Para un modelo con texturas, lo más fácil es entregar un `.glb` autocontenido. Mantén los modelos razonablemente ligeros para que el juego funcione bien en Chromebook.

## Publicación
El proyecto usa módulos de Three.js desde jsDelivr, por lo que necesita conexión a internet. En GitHub, comprueba **Settings → Pages** para verificar que Pages publique desde la rama `main` y la carpeta raíz.
