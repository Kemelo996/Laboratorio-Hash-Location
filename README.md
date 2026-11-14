# Laboratorio Hash Location

Aplicación Angular organizada por módulos de funcionalidad. Incluye la tabla de videojuegos y el módulo de personajes de Marvel Rivals. No requiere registro.

## Enrutamiento

La aplicación utiliza Hash Location Strategy (`useHash: true`) en el enrutador principal. Cada funcionalidad se carga desde su propio módulo:

- `/#/juegos`: catálogo tabular de videojuegos.
- `/#/marvel-rivals/list-marvel-rivals`: personajes de Marvel Rivals.
- `/#/lol/list-lol`: catálogo y tabla de campeones de League of Legends (módulo desarrollado por Kemelo996).

## Despliegue en GitHub Pages (Fork de Kemelo996)

El workflow automatizado en [.github/workflows/deploy.yml](.github/workflows/deploy.yml) compila y publica la aplicación en GitHub Pages:

- **Disparadores:** Activado en push a las ramas `develop` y `master`, además de `workflow_dispatch`.
- **Estrategia de Enrutamiento:** Emplea **HashLocationStrategy** (`{ useHash: true }`), lo que garantiza navegación fluida y recarga directa sin necesidad de configurar redirecciones o archivos de fallback 404 en GitHub Pages.
- **Pruebas y Verificación:** Ejecuta las pruebas unitarias con Jest (`npm test -- --runInBand --coverage=false`) y un job de verificación HTTP con reintentos para asegurar disponibilidad.

**Aplicación desplegada (Fork):** [https://kemelo996.github.io/Laboratorio-Hash-Location/](https://kemelo996.github.io/Laboratorio-Hash-Location/)

## Despliegue Original

El workflow de GitHub Actions construye la aplicación y la publica en GitHub Pages al actualizar la rama `master`.
El proyecto utiliza Angular 20 y Node.js 24 en el pipeline.

**Aplicación:** https://sebastian-henao.github.io/Laboratorio-Hash-Location/

Para compilar localmente:

```bash
npm ci
npm run build -- --base-href /Laboratorio-Hash-Location/
```
