# Primavera Growth Partners™

Landing page **estática** del programa de alianzas comerciales de **Primavera Events Group**.
Esta página presenta la vertical de espacios —**Venue Partners**— dirigida a dueños de salones
y jardines en Morelos.

No es una cotización: es una página comercial B2B permanente. Se publica en **GitHub Pages**
y se comparte con prospectos de alianza (dueños de venue) por Messenger, WhatsApp o correo.

---

## Origen y regla de diseño

Esta página **NO se diseñó desde cero**. Es una adaptación literal de
`C:\Users\Lenovo\Documents\cotizador-plantilla-universal\index.html`, la plantilla oficial
de cotizaciones de PEG, respetando `primavera brain/DIRECTIVES.md`.

**Regla permanente:** cualquier cambio visual debe seguir apareciéndose a las cotizaciones y
al sitio `primaveraeventsgroup.com`. Si una modificación rompe esa continuidad, está mal —
aunque se vea bonita por sí sola.

### Tokens de marca (DIRECTIVES.md §1 — no inventar colores)

| Token | Valor | Uso |
|---|---|---|
| `--primary-pink` | `#F65C7A` | Color principal, botones, iconos |
| `--primary-light` | `#FF8FA3` | Acentos secundarios |
| `--gold-accent` | `#C9A96E` | Líneas decorativas, badges premium |
| `--primary-dark` | `#1F1F1F` | Texto principal, fondos oscuros |
| `--background-light` | `#F8F6F4` | Fondo general |
| `--soft-pink` | `#FADADD` | Fondos suaves, badges |
| `--beige` | `#EFE7E1` | Bordes, separadores |
| `--gray-text` | `#6D6D6D` | Texto secundario |

Tipografía: **Playfair Display** (títulos) + **Poppins** (cuerpo), vía Google Fonts.
Iconos: Font Awesome 6.4.0 por CDN.
**PROHIBIDO:** café/marrón, rojos/azules/verdes planos, cualquier paleta fuera de Primavera.

### Estructura heredada de DIRECTIVES.md §2

Se conservaron los bloques obligatorios y se adaptaron a contenido B2B:

| # DIRECTIVES | En esta página |
|---|---|
| 1 Preloader | `precarga.mp4` + botón "Conocer el programa" |
| 2 Hero | Foto real de montaje con overlay oscuro |
| 3 Header info | Titular + `info-box` con 20 / 7 / 5 / 1 |
| 4 Logo | Logo PEG como botón-link a primaveraeventsgroup.com |
| 5 Galería | 4 fotos de producción real |
| 7 Desglose | Reemplazado por los **5 pilares** en `includes-grid` |
| 8 Bloque oscuro | Reemplazado por **Venue Residency™** |
| 10 Publicidad | Grid de 4 (XV, Bodas, Graduaciones, Planning) |
| 11 Kit Planner | Excel + PDF reales |
| 13 Firma | `firma.mp4` |
| 14 Notas | Sección de **transparencia** (no prometer ventas) |
| 15 CTA | WhatsApp "Quiero ser Venue Partner" |
| 16 Footer | Logo, contacto, derechos |

Se omitieron 6 (datos de salón), 9 (complementos) y 12 (botón PDF) por no aplicar a una
página de programa. El CSS de impresión sí se conservó y se ajustó.

---

## Archivos

Todos los assets van **sueltos en la raíz**, sin subcarpeta `assets/` (convención de PEG).

```
index.html
primavera-events-group-logo.png    ← logo PEG (NO usar primaveralogo.jpg = Banquetes Primavera)
precarga.mp4   firma.mp4   marcasonora.mp3
hero-venue.jpg
pilar-visibility.jpg  pilar-content.jpg  pilar-growth.jpg  pilar-network.jpg
serv-staffing.jpg  serv-activaciones.jpg  serv-montaje.jpg
serv-mobiliario.jpg  serv-mixologia.jpg  serv-cristaleria.jpg   (banco, sin usar aún)
galeria-1.jpg  galeria-2.jpg  galeria-3.jpg
pub-xv-anos.jpg  pub-bodas.jpg  pub-graduaciones.jpg  pub-planning.jpg
smart_event_planner_pro.xlsx   guia_maestra_primavera.pdf
```

Las fotos de evento provienen de `2026-09-05_XV-Elisa_CC-Presidente/Fotos_corregidas/`
(XV de Elisa, Centro de Convenciones Presidente), ya procesadas con el skill
`peg-photo-editorial`. Los `pub-*.jpg` y `serv-*.jpg` salen del banco de
`cotizador-plantilla-universal`.

---

## Repositorio y publicación

Este proyecto se desarrolla **de forma independiente** en:

```
C:\Users\Lenovo\Documents\PRIMAVERA GROWTH PARTNERS
```

Remoto: `git@github.com:5410m0n0c001/PRIMAVERA-GROWTH-PARTNERS.git`

> Nota de nombres (decisión de Salo, 2026-09-09): **Primavera Growth Partners™** es la marca
> paraguas del programa de alianzas — es la que encabeza la página y coincide con el nombre del
> repositorio. **Primavera Venue Partners™** es la vertical de venues que esta página presenta.
> El programa queda abierto a futuras verticales (proveedores, producción audiovisual, hospedaje)
> bajo la misma estructura de niveles y los mismos cinco pilares.

La carpeta `C:\Users\Lenovo\Documents\primavera-venue-partners` fue el borrador de origen
(sesión de `alexros brain`). **La fuente de verdad ahora es este repositorio** — no editar allá.

### Publicar

```bash
git push -u origin main
```

Después, activar Pages en GitHub (Settings -> Pages -> Branch `main`, carpeta `/root`).

URL resultante: `https://5410m0n0c001.github.io/PRIMAVERA-GROWTH-PARTNERS/`

`marcasonora.mp3` pesa ~5 MB; si el repo debe ir ligero, comprimirlo o quitar el audio de fondo.

---

## Datos: de dónde salen y qué NO tocar sin verificar

Todo dato duro de esta página se verificó contra **Supabase** (proyecto `fwqvkyeydykzleqowgqb`)
el 8 de septiembre de 2026, no contra memoria ni archivos locales sueltos.

- **Venues y URLs** → tabla `venues`, campos `url_oficial` y `es_oficial`.
  Solo se listan los que tienen `es_oficial = true`. Hay 20 registros en cartera y 7 oficiales.
- **Pareja venue ↔ paquete** → cruzada contra `playbook_comercial_manual_ventas.md`
  (sección "Bloques") en `conocimiento_rag_chunks`, **NO** contra `paquetes_servicios.metadata.venue`,
  que es texto libre y tiene errores confirmados.
  Correcto: **Los Potrillos = Linaje Pura Sangre** · **Los Caballos = Imperial Ecuestre**.
- **Contradicción registrada:** el playbook muestra `primaveraeventsgroup.com/jardin-la-flor/`,
  pero `venues` marca Jardín La Flor con `es_oficial = false` y `url_oficial = null`
  (verificado en vivo 2026-08-10). Gana la tabla verificada → **ese enlace no se usa**.
- **Expo Boda y 15 Años:** URL verificada en vivo el 2026-09-09 (existe, título "Expo Boda y Quince
  Años Centro De Convenciones Presidente"). **Primavera Haute Runway** aparece como entrada real del
  blog del sitio, pero no se enlaza porque no se capturó su URL exacta.
- **URLs sin verificar en vivo hoy:** ninguna pendiente crítica.
  Aparecen en tres fuentes locales coincidentes pero no se comprobaron con un fetch.
  **Verificarlas antes de publicar en producción.**
- **Zonas de cobertura:** derivadas de los municipios de los venues oficiales. "Asignada"
  = ya hay venue oficial ahí; "En evaluación" = hay espacio en cartera sin página;
  "Abierta" = sin presencia. Actualizar cuando cambie la cartera.

**Antes de tocar cualquier dato de PEG, invocar el skill `peg-verificar-datos`.** No es opcional.

---

## Pendientes conocidos

1. **Teléfono de WhatsApp** — se usa `527774587923`, tomado de la plantilla de cotizaciones.
   Confirmar con Salo si ese es el número correcto para prospectos de alianza B2B
   o si debe ir otro.
2. **Convenio de colaboración del Nivel III** — la página promete "vigencia definida, con piso
   de desempeño y salida clara", pero ese documento no existe todavía. Redactarlo antes de
   firmar con el primer Strategic Venue Partner.
3. **Costeo del Nivel III** — Resident Planner + gestión de redes es nómina real.
   Definir cuántos eventos al año hacen que un venue se pague solo antes de ofrecerlo.
4. **Formulario de postulación** — hoy el CTA va a WhatsApp. Si se quiere captar en la página,
   hace falta un backend o un servicio de formularios (no hay ninguno conectado).
5. **Fotos por venue** — la galería usa material del XV de Elisa en el CC Presidente.
   Convendría rotar con material de Zarabanda, Isabeles y Yolomecatl.
6. **Verificar Expo y Haute Runway en vivo** (ver arriba).

---

## Contexto de negocio (por qué está estructurado así)

- **No se vende "manejo de redes".** Eso mete a PEG en la categoría de agencia, donde se
  compite por precio. Se vende **alianza de crecimiento y comercialización**, con el marketing
  como uno de cinco pilares.
- **Tres niveles** (Venue Partner / Preferred Venue / Strategic Venue Partner) porque la
  gestión integral de redes es lo más caro que ofrece PEG: no puede ser el gancho de entrada,
  va amarrada a exclusividad en el Nivel III.
- **Exclusividad mutua, no unilateral.** Si PEG absorbe marketing y contenido y el venue queda
  libre, PEG financia la promoción de un espacio que después vende otro. Se formula elegante:
  *"venue estratégico de Primavera en su zona de influencia"*, no "exclusividad absoluta".
- **Escasez territorial real** — la tabla de zonas abiertas es el motor de urgencia.
- **No prometer ventas.** Sección de transparencia explícita: PEG compromete demanda,
  posicionamiento y desarrollo comercial; el cierre depende también del precio, servicio,
  disponibilidad y capacidad de respuesta del venue.

---

*Documento generado el 8 de septiembre de 2026. Repo pertenece a Salomón Ramírez Ortega
(GitHub: 5410m0n0c001) para Primavera Events Group.*
