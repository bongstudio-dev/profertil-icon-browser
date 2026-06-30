# Profertil · Icon Browser

Herramienta web estática (HTML + CSS + JS vanilla, sin build step) para explorar, filtrar, recolorear y exportar la librería de íconos del **Sistema de marca Profertil 2026**. Comparte el lenguaje visual del [Profertil Pattern Generator](https://github.com/bongstudio-dev/profertil-pattern-generator).

## Uso

```bash
cd profertil-icon-browser
python3 -m http.server 5050     # o: npm run dev
# abrí http://localhost:5050
```

> Los íconos están embebidos en `icons-data.js`, así que la app también funciona abriendo `index.html` directamente (doble click), sin servidor.

## Funcionalidad

- **194 íconos** en 8 categorías: Administración, Agro, Compliance, Industria, Personas, Planta, Sostenibilidad, Supply Chain.
- **Búsqueda** en tiempo real por nombre / categoría.
- **Recoloreo global** con 3 pills: Original (blanco), Azul `#003DA5`, Verde `#2D8035`.
- **Modal por ícono** con preview grande, selector de color y export **SVG** / **PNG** (512×512).
- **Export masivo** a `.zip` (JSZip) de la selección actual en el color elegido.

## Cómo funciona el recoloreo

Los SVGs originales usan `stroke="white"` / `fill="white"` hardcodeado. El script de build (`build-data.py`) los convierte a `currentColor`, de modo que el color se controla por CSS (`color`) y se "hornea" al exportar. Como el original es blanco, el modo **Original** se muestra sobre un tile azul para que el ícono sea visible.

## Regenerar la data

Si cambian los SVGs fuente (carpetas hermanas de este proyecto):

```bash
python3 build-data.py     # o: npm run build:data
```

Regenera `icons-data.js` y copia los SVGs a `public/iconos/`.

---

Sistema de íconos por **[Bong](https://bongstudio.ar)**.
