# Modulo 8 - Cloud (Laboratorio)

Proyecto base con React + Vite para completar el laboratorio.

## Requisitos

- Node.js 20+
- Git
- Repositorio en GitHub

## Ejecutar en local

1. Instalar dependencias:

```bash
npm install
```

2. Levantar en desarrollo:

```bash
npm run dev
```

## 1) Despliegue manual (sin Actions)

Esta parte te cubre el punto de despliegue manual del laboratorio.

1. Genera la build:

```bash
npm run build
```

2. Publica `dist` en la rama `gh-pages` (manual):

```bash
git add dist -f
git commit -m "build manual para pages"
git subtree split --prefix dist -b gh-pages
git push origin gh-pages --force
git branch -D gh-pages
```

3. En GitHub: `Settings` -> `Pages`.
4. Configura `Source`: `Deploy from a branch`.
5. Selecciona rama `gh-pages` y carpeta `/ (root)`.
6. Guarda y valida la URL publicada.

## 2) Despliegue automatico con GitHub Actions

El workflow esta en `.github/workflows/deploy-pages.yml` y hace:

1. Checkout.
2. Setup Node.
3. `npm install`.
4. `npm run build`.
5. Publica `dist` en GitHub Pages.

Pasos:

1. En GitHub: `Settings` -> `Pages`.
2. Cambia `Source` a `GitHub Actions`.
3. Haz un cambio y push a `main`.
4. Revisa `Actions` -> workflow `Deploy to GitHub Pages`.
5. Comprueba la URL final.

## Entrega recomendada

1. Captura del despliegue manual (`gh-pages`).
2. Captura de la URL publica funcionando.
3. Captura del workflow en verde en `Actions`.
4. Captura de la URL actualizada tras nuevo push.
