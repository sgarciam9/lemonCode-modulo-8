# Modulo 8 - Cloud (Laboratorio)

Repositorio del laboratorio del modulo Cloud con una app React + Vite desplegada en GitHub Pages.

## Objetivos del ejercicio

1. Realizar un despliegue manual en GitHub Pages.
2. Automatizar build y despliegue con GitHub Actions al hacer push/merge a `main`.

## Stack del proyecto

- React 18
- Vite 5
- GitHub Pages
- GitHub Actions

## Estructura relevante

- `src/App.jsx`: componente principal.
- `src/main.jsx`: punto de entrada de React.
- `vite.config.js`: configura `base` dinamicamente para Pages.
- `.github/workflows/deploy-pages.yml`: workflow de build y deploy.

## Requisitos

- Node.js 20+
- npm
- Git
- Repositorio en GitHub

## Ejecutar en local

1. Instalar dependencias:

```bash
npm install
```

2. Ejecutar entorno de desarrollo:

```bash
npm run dev
```

3. Generar build de produccion:

```bash
npm run build
```

## Despliegue manual (GitHub Pages)

Este flujo cubre la parte manual del laboratorio.

1. Generar la build:

```bash
npm run build
```

2. Publicar `dist` en `gh-pages`:

```bash
git add dist -f
git commit -m "build manual para pages"
git subtree split --prefix dist -b gh-pages
git push origin gh-pages --force
git branch -D gh-pages
```

3. En GitHub, ir a `Settings -> Pages`.
4. Seleccionar:
   - `Source`: `Deploy from a branch`
   - `Branch`: `gh-pages` y carpeta `/ (root)`
5. Guardar y validar la URL publicada.

## Despliegue automatico (GitHub Actions)

Workflow usado: `.github/workflows/deploy-pages.yml`

Se ejecuta con:

- push a `main`
- ejecucion manual (`workflow_dispatch`)

Pasos del workflow:

1. Checkout del repositorio.
2. Setup Node.js 20.
3. Instalacion de dependencias con `npm ci`.
4. Build con `npm run build`.
5. Publicacion de artefacto `dist`.
6. Deploy a entorno `github-pages`.

Configuracion en GitHub:

1. Ir a `Settings -> Pages`.
2. En `Source`, elegir `GitHub Actions`.
3. Hacer push a `main` o lanzar `Run workflow`.
4. Verificar ejecucion en `Actions`.

## URL publicada

- `https://sgarciam9.github.io/lemonCode-modulo-8/`

## Comandos utiles

Ver estado:

```bash
git status
```

Subir cambios:

```bash
git add .
git commit -m "mensaje"
git push origin main
```

Forzar ejecucion del workflow sin cambios funcionales:

```bash
git commit --allow-empty -m "trigger pages workflow"
git push origin main
```

## Evidencias para entrega

1. Captura de `Settings -> Pages` configurado.
2. Captura de `Actions` con workflow en verde.
3. Captura de la URL publica funcionando.
4. Captura de un nuevo despliegue tras push a `main`.

## Documento de entrega

- Ver `ENTREGA.md` para el informe listo para presentar.
