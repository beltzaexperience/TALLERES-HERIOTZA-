# 13 RITUALES · EJERCICIOS BELTZA — NOTAS DE PROYECTO

## Repositorio
```
https://github.com/beltzaexperience/13-RITUALES
https://beltzaexperience.github.io/13-RITUALES/
```

## Estructura de archivos
```
13-RITUALES/
├── index.html                     ← homepage 13 Rituales
├── style.css                      ← estilos separados (pluma Apache)
├── logo13.png                     ← logo 13 extraído del Manifiesto
├── beltza-puno.png                ← logo puño Beltza
├── rastros-jupiter-05-26.html     ← cartel Rastros de Júpiter Mayo 2026
└── (futuros carteles .html)
```

## Red de proyectos Beltza Experience
| Proyecto | URL | Repo |
|---|---|---|
| Manifiesto | beltzaexperience.github.io/Manifiesto-Beltza/ | Manifiesto-Beltza |
| UR-SAPIENS | beltzaexperience.github.io/UR-SAPIENS/ | UR-SAPIENS |
| Magic Bus | beltzaexperience.github.io/magic-bus/ | magic-bus |
| 13 Rituales | beltzaexperience.github.io/13-RITUALES/ | 13-RITUALES |
| DUB²BEAT | dubbeat.beltzarecords.com | DUB2BEAT-PHOTOGRAPHY |
| beltzarecords.com | www.beltzarecords.com | (servidor Karlos) |

---

## Paleta y tipografías

### Colores
```css
--black:  #0a0a0a   /* fondo principal */
--white:  #f2ede6   /* texto principal */
--red:    #b01a1a   /* rojo sangre */
--amber:  #c8922a   /* ámbar links */
--muted:  #666      /* texto secundario */
```
Color intro: `#82C8E5` (azul cielo)
Color cartel Rastros: `#142240` (azul marino) · fondo web cartel: `#0F4336` (verde musgo)

### Tipografías (Google Fonts)
- **Bebas Neue** — títulos, brand slash, topband, labels
- **Courier Prime** — cuerpo de texto, captions
- **Playfair Display** — títulos hero

---

## Estructura del index.html

### 1. TOPBAND
```
BELTZARECORDS.COM · DONOSTIA _ DONEZTEBE  |  MANIFIESTO · MAGIC BUS · DUB²BEAT · UR-SAPIENS
```
- Font: Bebas Neue `clamp(1.07rem,2.25vw,1.47rem)` · letter-spacing: 0.15em
- Padding: `1.1rem clamp(1rem,4vw,3rem)`
- Links en ámbar · `²` de DUB en rojo · `flex-wrap:wrap`

### 2. BRAND SLASH (fondo rojo)
```
[logo13.png]  &nbsp;&nbsp;  RITUALES  &nbsp;&nbsp;  +  &nbsp;&nbsp;  EJERCICIOS  &nbsp;&nbsp;  BELTZA  &nbsp;&nbsp;  [beltza-puno.png]
```
- Separadores: `&nbsp;&nbsp;` entre cada elemento
- Logo 13: `logo13.png` · `clamp(3.2rem,9vw,8rem)`
- RITUALES / EJERCICIOS: `.b-eventos` — Bebas Neue caja negra texto rojo
- `+`: blanco · `clamp(5rem,14vw,12rem)`
- BELTZA: sin caja · negro · `clamp(2.8rem,7.8vw,6.5rem)`
- Puño: `beltza-puno.png` desde repo
- Todo centrado: `justify-content:center`

### 3. MARQUEE TOP (fondo negro)
- Texto blanco · mismo tamaño topband · mismo padding
- Contenido: 13 RITUALES · EJERCICIOS BELTZA · BROCANTE · MÚSICA...

### 4. HERO (foto completa sin recorte)
- Foto: Ultramarinos Parroquia 13 fachada + letrero verde
- **Texto arriba** `.hero-eyebrow-top` — rojo negrita:
  `Doneztebe · Nafarroa / Azken Muga of Soul`
- **Texto abajo** `.hero-title` — Playfair itálica blanca:
  `Rituales de CultURa Popular. / Ejercicios del Espíritu Beltza.`
  (UR en rojo)

### 5. INTRO (fondo azul #82C8E5)
- Label rojo: `Ejercicios Espirituales de Cult ur a Popular · Doneztebe · Nafarroa`
- Cuerpo: texto Vudú-Beat, Xabatenea Etxea, Ritualismo POP, Smart Dress Style
- Ancho completo, sin columna lateral

### 6. PHOTO MARQUEE
- Clase: `.foto-marquee-wrap` / `.foto-marquee-track`
- Velocidad: 60s (lento)
- Franjas rojas 7px arriba y abajo
- Arranca solo tras `window.load` (espera a que carguen las fotos)
- Sin pausa por click (conflictos resueltos eliminando toggle)
- 18 fotos únicas mezcladas en random, duplicadas para loop suave

### 7. EVENTS GRID (masonry)
- `columns: 3` · 2 en tablet · 1 en móvil
- Cada tarjeta: borde rojo 2px · padding 4px interior
- Pie de foto fondo `#142240` (azul cartel)
- Título: Bebas blanco · `flex:1` · `text-overflow:ellipsis`
- Link: **Ver →** en ámbar · `flex-shrink:0`
- Contador dinámico `001` — suma automáticamente con cada cartel añadido

### 8. MARQUEE BOTTOM
- Mismo estilo que marquee top
- Línea roja 4px encima
- Velocidad: 55s

### 9. FOOTER (clon de topband)
- Misma estructura y tamaño que topband
- Línea roja 4px encima
- Coords: `clamp(0.95rem,1.6vw,1.2rem)` en blanco

---

## CSS — Clases principales

| Clase | Uso |
|---|---|
| `.topband` | Barra superior/inferior navegación |
| `.brand-slash` | Título principal rojo |
| `.b-eventos` | Bebas caja negra texto rojo |
| `.marquee-bar / .marquee-inner` | Marquee texto |
| `.hero` | Foto completa sin recorte |
| `.hero-eyebrow-top` | Texto rojo arriba foto |
| `.hero-title` | Título Playfair abajo foto |
| `.intro` | Sección azul con texto |
| `.foto-marquee-wrap / .foto-marquee-track` | Marquee de fotos |
| `.events-section` | Sección grid masonry |
| `.event-card` | Tarjeta cartel |
| `.event-card-body` | Pie azul de tarjeta |
| `.footer` | Footer clon topband |
| `.footer-coords` | Coordenadas GPS blancas |

---

## Carteles — Convención de nombres
```
nombre-evento-MM-AA.html
```
Ejemplo: `rastros-jupiter-05-26.html`

### Carteles existentes
| Archivo | Evento | Fecha |
|---|---|---|
| `rastros-jupiter-05-26.html` | 4º Aniversario Los Rastros de Júpiter | 30 Mayo 2026 |

### Añadir nuevo cartel
1. Subir `.html` al repo 13-RITUALES con la convención de nombres
2. Añadir tarjeta en `.events-grid` del `index.html`
3. El contador `001` sube automáticamente
4. Actualizar link en Magic Bus si tiene post

---

## Cartel rastros-jupiter-05-26.html
- Fondo web: `#0F4336` (verde musgo) — inline en `<style>` del `<head>`
- Sin `link` a `style.css` externo — todo inline
- `image.jpg` carga desde el mismo repo 13-RITUALES
- Viewport `width=1100` + `scaleCartel()` para móvil

---

## Mobile
- Topband: `flex-wrap:wrap` — fluye en varias líneas
- Brand slash: `flex-wrap:wrap` desde 700px
- Events grid: 2 col móvil · 1 col en 420px
- Hero: foto completa, texto posicionado absolute

---

## GitHub — Seguridad
- Solo tú puedes modificar/borrar (con tu cuenta)
- Código visible en público — normal, no es riesgo
- Para repos privados con Pages → GitHub Pro ~4€/mes

## CNAME — URL personalizada
1. Archivo `CNAME` en raíz del repo: `rituales.beltzarecords.com`
2. Karlos: registro DNS CNAME `rituales` → `beltzaexperience.github.io`
3. GitHub Settings → Pages → Custom domain

---

## Fonema UR — Identidad Visual Beltza
El fonema **UR** aparece en rojo `#b01a1a` en todo el texto visible.
```html
Cult<span style="color:#b01a1a;">ur</span>a
CULT<span style="color:#b01a1a;">UR</span>ALES
```

## Magic Bus — Post Rastros de Júpiter
- ID: `rastros-4-aniversario`
- Link cartel: `https://beltzaexperience.github.io/13-RITUALES/rastros-jupiter-05-26.html`
- Comentario: **CLAUDIUS · Siglo I d.C. · Vía Láctea, Brazo de Orión**
- Número: Magic Bus Nº2 · Secundus
