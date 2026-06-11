# Francisco Leitão — sitio personal

Página de una sola pantalla que presenta a Francisco Leitão como experto, con sus áreas de expertise enlazadas a páginas propias y su trayectoria. Sitio estático (un `index.html`, sin build), listo para Vercel.

## Estructura

```
francisco-leitao/
├── index.html
└── README.md
```

## Activar el enlace de cada área

Por defecto, solo "Marketing de Afiliados" está enlazado (a `https://marketing-de-afiliados.vercel.app`). El resto aparece como "Próximamente".

Para activar una tarjeta cuando su página esté lista, en `index.html` busca el `<div class="area is-soon">` correspondiente y cámbialo por un enlace:

```html
<!-- ANTES -->
<div class="area is-soon" role="article">
  <span class="tag">Performance</span>
  <h3>Paid Media</h3>
  <p>...</p>
  <span class="go soon">Próximamente</span>
</div>

<!-- DESPUÉS -->
<a class="area" href="https://paid-media.vercel.app" target="_blank" rel="noopener">
  <span class="tag">Performance</span>
  <h3>Paid Media</h3>
  <p>...</p>
  <span class="go active">Ver más <span class="ar">↗</span></span>
</a>
```

Es decir: `<div ... is-soon>` → `<a ... href="TU-URL">`, y `<span class="go soon">Próximamente</span>` → `<span class="go active">Ver más <span class="ar">↗</span></span>`.

## Subir a GitHub

```bash
cd francisco-leitao
git init
git add .
git commit -m "Sitio personal de Francisco Leitão"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/francisco-leitao.git
git push -u origin main
```

## Desplegar en Vercel

1. Entra a vercel.com con tu cuenta de GitHub.
2. **Add New → Project** y selecciona el repo.
3. Framework Preset: **Other**. Build Command y Output Directory vacíos.
4. **Deploy**. Cada `git push` a `main` redespliega solo.

## Personalizar

- **Color:** las variables `--violet` y `--cyan` al inicio del `<style>` controlan toda la paleta.
- **Contacto:** hoy el contacto va a LinkedIn. Si quieres agregar email o WhatsApp, duplica el botón en la sección `#contacto` con `href="mailto:tucorreo"` o `href="https://wa.me/56..."`.
- **Trayectoria:** edita las listas de la sección `#trayectoria` con tus datos exactos (cargos, fechas).
