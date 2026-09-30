# Brief + Prompts — Collage del hero Envíos Express · 2026-09-30

Reemplaza las dos imágenes del collage de **`/servicios/envios-express`** (`src/components/servicios/express/ExpressHeroCollage.tsx`). Deja sin efecto la entrada `servicio-express` de `servicio-express.md`, que describe la tarjeta vieja (`bg-brand-blue-900`) y el cronómetro de "60 a 90 min" retirado el 2026-09-29.

- **Generar:** `python docs/imagenes/hero-derecha/generate.py --prompts docs/imagenes/hero-derecha/express-collage.md express-ruta express-franja`
- **Salida:** `public/img/heroes/express-ruta.webp` y `public/img/heroes/express-franja.webp` (recorte por chroma key incluido).
- **Promesa vigente** (`src/lib/promises.ts`): `EXPRESS_WINDOW = 'franja horaria de 3 hs'`, `EXPRESS_CUTOFF_TIME = '15:00 hs'`. Ninguna cifra va dentro de la imagen: el collage ya las muestra en las teselas "3 hs" y "Corte 15:00 hs".

## Lectura del collage

| Tesela | Hueco en código | Fondo de la tesela | Hoy | Problema |
| --- | --- | --- | --- | --- |
| `moto` | `aspect-[560/262]` (≈2,14:1), 400 px en desktop, `priority` | `bg-brand-blue-50` (#E6EEFE) | `/heroes/express-moto.webp`, 560×373 | Tiene "ENVÍOS EN EL DÍA" horneado y se esconde con `object-top`, que además corta la base del diorama. 560 px se ve borroso en pantallas 2x. El mensaje ya no es la promesa vigente |
| `rider` | `aspect-[1408/768]` (≈1,83:1), 360 px en desktop | `bg-brand-blue-400` (#3570F8) | `/img/generales/repartidor.webp`, foto hiperrealista IA en duotono | Mezcla foto con el render 3D de la tesela `moto`; figura humana realista IA (radar: Evitar); "ENVIOS EXPRESS" horneado en el top box |

## Prompts

### express-ruta

- **Uso:** tesela `moto` — la ruta directa, sin paradas
- **Referencias:** `public/img/generales/card_moto01.webp` · `docs/imagenes/hero-derecha/referencias/logo-master-1024.png`
- **Aspect ratio:** `21:9`
- **Superficie:** pale blue #E6EEFE
- **Idea:** retiro en un punto, entrega en otro, nada en el medio.

```text
[Subject] A long, shallow rounded-rectangle isometric diorama strip with a thick bevelled sky-blue edge, carrying one straight street that runs across its full length between low matte city blocks with pale-blue rooftops. At the left end, a small faceted blue origin pin stands in front of a tiny corner shop with an open shutter; at the right end, the street ends at the front door of a small stone-front seaside chalet with a pale-blue roof. A thick glossy route tube in signal yellow with a tight emissive core runs straight from the pin to the door, with no branches and no other stops. One DosRuedas delivery scooter rides along it, a little left of center, leaning forward at speed. Match the scooter to the first reference image — a classic underbone step-through city scooter with round mirrors, spoked wheels and a large rear top box, same proportions and chunky clay look — recolored: body bright blue, lower panels sky blue, wheel rims and mirror housings signal yellow, and the top box signal yellow with rounded sky-blue bevels and a thin band of small alternating blue and white squares around its lid, taken from the second reference image. The rider is a stylized faceless vinyl-toy figure in a blue polo with a yellow collar and a pale-blue helmet with a fully closed tinted sky-blue visor. Along the far edge of the strip, a narrow band of stylized glossy blue sea with soft rounded waves.
[Style] Modern 3D isometric miniature diorama render, soft matte clay and satin plastic materials, rounded bevelled edges, chunky simplified geometry, subtle glossy highlights only on the scooter and the top box, premium Blender Cycles / Octane product-render look. The reference images define object identity and brand motifs only, never the composition, the background or any text.
[Palette] Base material colors ONLY: bright blue #0950F6 for main volumes (scooter body, city blocks), blue #3570F8 and sky blue #628FF9 for side faces and the diorama edge, pale blue #E6EEFE and white #FFFFFF for rooftops, street surface and highlights, signal yellow #FFEC01 as the single accent (route, rims, top box) covering at most 15% of the image. The object sits on a pale blue #E6EEFE card, so the diorama edge and main volumes must stay saturated blue to separate from it. Nothing anywhere darker than #0950F6, not even crevices or shadows. No navy, no black.
[Lighting] Soft studio three-point lighting: large cool-white key light from the upper left, gentle fill, thin white rim light; soft ambient occlusion tinted light blue, never black; every contact shadow falls on the diorama base only; tight emissive glow only on the yellow route.
[Composition] Isometric three-quarter view from 30 degrees above, the street running horizontally from left to right across the frame. Ultra-wide 21:9, the strip fills about 84% of the width with at least 8% empty margin on the left and right and 10% at top and bottom, fully contained, nothing cropped, vertically centered. Bold readable silhouette at 400px wide.
[Quality] 8k ultra-detailed, crisp clean edges, noise-free high-end product render.
[Background] Solid flat uniform unlit chroma key magenta #FF00FF filling the entire canvas edge to edge, not reflected on and not lighting the subject, for transparent cutout.
[Negative] No text, no letters, no numbers, no phone numbers, no social media icons, no logo badge, no brand name, no license plate, no watermark, no magenta, pink or purple tint or reflections on the subject, no green, no red, no orange, no grey or charcoal surfaces, no black, no dark navy, no chrome or mirror metal, no bloom spilling beyond the objects, no shadows on the background, no realistic human, no visible face, no brown cardboard, no multiple parcels, no other vehicles, no traffic, no intermediate stops or branching routes, no clocks, no flat vector, no cartoon outlines, no cyberpunk neon, no depth-of-field blur, no motion blur, nothing cropped.
```

### express-franja

- **Uso:** tesela `rider` — la entrega en la puerta, dentro de la franja elegida
- **Referencias:** `public/img/generales/card_moto01.webp` · `public/cards/hero_express.webp`
- **Aspect ratio:** `16:9`
- **Superficie:** blue #3570F8
- **Idea:** llega a la puerta dentro del horario que eligió el cliente.

```text
[Subject] A compact isometric diorama tile with a thick bevelled pale-blue edge showing the front of a small stone-front Mar del Plata chalet with a pale-blue roof and an open front door. On the doorstep, a stylized faceless vinyl-toy courier hands over one small parcel wrapped in pale blue with a signal-yellow tape seal. The courier wears the uniform from the second reference image — blue polo with a yellow collar and a blue cap with a yellow visor — as a rounded toy figure with a smooth featureless head, no face. At the curb, the DosRuedas scooter from the first reference image stands parked, recolored: body bright blue, lower panels sky blue, rims signal yellow, top box signal yellow with rounded sky-blue bevels. Floating above the door, a large chunky 3D clock ring in white and pale blue with no numerals and no hands, where one signal-yellow arc covering exactly one quarter of the dial glows softly, marking the chosen delivery window. A small yellow check mark hovers by the door.
[Style] Modern 3D isometric miniature diorama render, soft matte clay and satin plastic materials, rounded bevelled edges, chunky simplified geometry, subtle glossy highlights only on the clock ring and the parcel, premium Blender Cycles / Octane product-render look. The reference images define object identity only, never the composition, the background, the face or any text.
[Palette] Base material colors ONLY: white #FFFFFF and pale blue #E6EEFE for main volumes and top faces, light blue #8EAFFB and sky blue #628FF9 for side faces and the diorama edge, signal yellow #FFEC01 as the single accent (clock arc, tape, rims, top box, check) covering at most 15% of the image. The darkest tone anywhere is bright blue #0950F6, used only in small details such as the polo and the scooter body. The object sits on a blue #3570F8 card and must read light and bright against it. No navy, no black.
[Lighting] Soft studio three-point lighting: large cool-white key light from the upper left, gentle fill, thin white rim light; soft ambient occlusion tinted light blue, never black; every contact shadow falls on the diorama base only; soft emissive glow only on the yellow clock arc.
[Composition] Isometric three-quarter view from 30 degrees above, centered. Horizontal 16:9, subject fills about 76% of the width with at least 9% empty margin on every side, the clock ring in the upper third above the door, the courier and parcel as the focal point in the center, the scooter on the left. Fully contained, nothing cropped, bold readable silhouette at 360px wide.
[Quality] 8k ultra-detailed, crisp clean edges, noise-free high-end product render.
[Background] Solid flat uniform unlit chroma key magenta #FF00FF filling the entire canvas edge to edge, not reflected on and not lighting the subject, for transparent cutout.
[Negative] No text, no letters, no numbers, no clock numerals, no clock hands, no tick labels, no phone numbers, no social media icons, no logo badge, no brand name, no license plate, no watermark, no magenta, pink or purple tint or reflections on the subject, no green, no red, no orange, no grey or charcoal surfaces, no black, no dark navy, no realistic human, no visible face, no brown cardboard, no multiple parcels, no other vehicles, no flat vector, no cartoon outlines, no cyberpunk neon, no depth-of-field blur, no motion blur, nothing cropped.
```

## Cambios en `ExpressHeroCollage.tsx` al publicar las imágenes

- Tesela `moto`: `src="/img/heroes/express-ruta.webp"` y `className="object-cover object-center"` (ya no hay texto que esconder).
- Tesela `rider`: `src="/img/heroes/express-franja.webp"` y `className="object-cover"`. Sacar `grayscale contrast-[1.05] mix-blend-screen`: el filtro le borra el amarillo al render. Actualizar el comentario del duotono.
- Alt: las dos quedan con `alt=""`; el collage es `aria-hidden` y el mensaje lo da el `<h1>`.

## Variante A/B (señal 4 de `CONTEXTO-VISUAL.md`)

Los posteos con la flota real en la calle rinden más que los gráficos. Si el dueño aporta fotos reales de sus motos y repartidores (con autorización), la variante B usa **las dos teselas en foto real** con el duotono actual, nunca una foto junto a un render. No hay fotos reales en el repo: `repartidor.webp` y `public/cards/hero_express.webp` son generadas.
