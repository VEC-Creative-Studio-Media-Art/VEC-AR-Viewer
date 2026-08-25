# Galería AR — Guía rápida

## 1. Estructura de archivos

```
ar-app/
├── index.html
└── models/
    ├── modelo1.glb     ← para Android / navegadores WebXR
    └── modelo1.usdz    ← para iPhone / iPad (Quick Look)
```

**Importante:** para que el AR funcione en TODOS los celulares necesitas
**ambos formatos** del mismo modelo:

- `.glb` → Android (Scene Viewer) y web de escritorio
- `.usdz` → iOS (Quick Look)

Si solo tienes `.glb`, hay convertidores gratuitos:
- https://products.aspose.app/3d/conversion/glb-to-usdz
- Reality Converter (Mac, gratis, de Apple)

## 2. Agregar tus modelos

1. Copia tus archivos `.glb` y `.usdz` dentro de `models/`.
2. En `index.html`, duplica el bloque `<div class="card">...</div>`
   por cada modelo, y cambia:
   - `src="models/TU_ARCHIVO.glb"`
   - `ios-src="models/TU_ARCHIVO.usdz"`
   - el título y descripción en `.card-info`

## 3. Requisitos de los modelos (para que el AR se vea bien)

- Tamaño real: modela/escala tus objetos a su tamaño real en metros
  (AR coloca el objeto a escala 1:1 en el mundo real).
- Peso recomendado: menos de 15-20 MB por modelo para que cargue rápido
  en datos móviles.
- Formato de texturas: usa JPG/PNG comprimidos, evita texturas 4K si no
  son necesarias.

## 4. Hostear en línea (gratis)

### Opción recomendada: Netlify (arrastrar y soltar)
1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta `ar-app` completa a la página
3. Netlify te da una URL pública al instante (ej: `tuapp.netlify.app`)
4. Ya puedes compartir ese link — funciona en cualquier celular

### Alternativa: GitHub Pages
1. Sube la carpeta a un repositorio de GitHub
2. Ve a Settings → Pages → selecciona la rama `main` y carpeta `/root`
3. Tu app queda en `https://tu-usuario.github.io/tu-repo/`

### Alternativa: Vercel
1. https://vercel.com → "Add New Project" → sube la carpeta
2. Deploy automático, te da una URL pública

**Nota técnica:** AR en móviles requiere HTTPS (no funciona en `http://`
plano). Los tres servicios de arriba dan HTTPS automáticamente, así que
no tienes que configurar nada extra.

## 5. Probarlo

- En Android: abre el link en Chrome, toca "Ver en tu espacio"
- En iPhone: abre el link en Safari (no en Chrome), toca el botón AR
- En escritorio: verás el modelo 3D interactivo, pero sin botón AR
  (el AR solo aparece en celulares compatibles)
