# Mouse FPV 360°

Demo web de una vista en primera persona controlada por el mouse usando Three.js y un panorama equirectangular de 360°.

## Ejecutar
- Abre `index.html` en un navegador moderno con conexión a internet. Si el navegador bloquea módulos al abrir archivos locales, inicia un servidor local:
  - Python: `python -m http.server 8000`
  - Luego visita `http://localhost:8000`.

## Controles
- Mueve el mouse para cambiar la dirección de la mirada.
- Usa la rueda para cambiar el campo de visión (zoom).
- Usa **Activar modo arrastre** si prefieres girar manteniendo pulsado.
- **Centrar vista** devuelve la cámara al frente.
- **Pantalla completa** amplía la experiencia.

## Cambiar la imagen 360°
En `index.html`, cambia la constante `panoramaUrl` por la URL pública de tu imagen panorámica equirectangular (relación de aspecto aproximada 2:1). La imagen se carga desde internet; el proyecto incluye un entorno de respaldo si no puede descargarse.

## Publicar en GitHub Pages
1. Crea un repositorio público en GitHub.
2. Sube `index.html` y `README.md` a la raíz.
3. Ve a **Settings → Pages**.
4. En **Build and deployment**, selecciona **Deploy from a branch**, rama `main` y carpeta `/ (root)`.
5. Guarda y espera a que GitHub muestre la URL publicada.
