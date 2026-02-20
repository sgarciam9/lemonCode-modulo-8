# Entrega - Laboratorio Modulo 8 Cloud

## Alumno

- Nombre: Sergio Garcia (completar si aplica)
- Repositorio: `https://github.com/sgarciam9/lemonCode-modulo-8`
- Fecha: 20/02/2026

## Resumen

En este laboratorio se ha desplegado una aplicacion React + Vite en GitHub Pages, primero de forma manual y posteriormente mediante un flujo automatizado con GitHub Actions.

## Objetivos completados

1. Despliegue manual en GitHub Pages.
2. Automatizacion de build y deploy al actualizar la rama `main`.

## Implementacion tecnica

### Aplicacion

- Framework: React.
- Bundler: Vite.
- Configuracion clave para Pages: `vite.config.js` con `base` del repositorio.

### Workflow CI/CD

Archivo: `.github/workflows/deploy-pages.yml`

El pipeline realiza:

1. Checkout del codigo.
2. Configuracion de Node.js.
3. Instalacion con `npm ci`.
4. Compilacion con `npm run build`.
5. Publicacion de `dist` como artefacto.
6. Despliegue en `github-pages`.

## Resultado

- URL final publicada:
  - `https://sgarciam9.github.io/lemonCode-modulo-8/`
- Estado de workflow:
  - Ejecuciones correctas en verde en la pestana Actions.

## Evidencias adjuntas

1. GitHub Pages configurado.
2. Workflow `Deploy to GitHub Pages` ejecutado correctamente.
3. Sitio web accesible desde la URL publica.
4. Nuevo despliegue correcto tras push adicional.

## Incidencias y resolucion

- Incidencia: al principio no aparecia el workflow en Actions por estar en la vista de plantillas.
- Resolucion: acceso directo al workflow del repo y ejecucion manual/por push a `main`.

## Conclusion

Se han cumplido los requisitos del laboratorio, quedando operativo un flujo completo de despliegue manual y automatico en GitHub Pages.
