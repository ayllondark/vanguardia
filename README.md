# Sistema DEVANO — ERP Web

Aplicación web (ERP) para DEVANO S.A.C.: gestión de inventario y costeo, cotizaciones
con generación de PDF, panel de indicadores, reportes de rentabilidad, proveedores y
administración de usuarios con accesos por rol (Administrador, Vendedor, Almacén).

Es un sitio **estático**, sin paso de compilación: todo vive en [`index.html`](index.html)
(HTML + CSS + JavaScript vanilla, sin dependencias salvo Google Fonts).

## Ejecutar en local

Basta con abrir el archivo en el navegador:

```bash
# Windows
start index.html
```

O servirlo con cualquier servidor estático, por ejemplo:

```bash
npx serve .
```

## Desplegar en Vercel

El proyecto ya está configurado como sitio estático mediante [`vercel.json`](vercel.json).
No requiere `build`; Vercel lo detecta como proyecto **Other / Static**.

### Opción A — Conectar el repositorio (recomendado)

1. Entra a https://vercel.com/new
2. Importa el repositorio de GitHub: `ayllondark/vanguardia`.
3. **Framework Preset:** `Other`. **Build Command:** *(vacío)*. **Output Directory:** *(vacío / raíz)*.
4. Deploy. Cada `git push` a `master` genera un nuevo despliegue automático.

### Opción B — CLI de Vercel

```bash
npm i -g vercel
vercel          # primer despliegue (preview)
vercel --prod   # despliegue a producción
```

## Privacidad de la proforma

La proforma comercial (`Proforma-MINDOOS-DEVANO.pdf` y `proforma-devano.html`) contiene
precios y RUCs, por lo que **se excluye del despliegue** mediante [`.vercelignore`](.vercelignore).
Permanece en el repositorio/local, pero no se publica en el sitio de Vercel.
