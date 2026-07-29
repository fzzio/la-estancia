# Frames Run Pack — Hook 60s "La Estancia"

Orden de ejecución obligatorio. NO saltarse el paso 0.

## Herramientas y por qué

- **Nano Banana** (Gemini 2.5 Flash Image en Google AI Studio): gratis con cuota generosa, acepta imagen de referencia + prompt para editar/regenerar preservando personaje. **Es la herramienta principal aquí**. https://aistudio.google.com/ → "Try Gemini" → seleccionar modelo `gemini-2.5-flash-image`
- **Midjourney** (opcional, plan mínimo $10/mes): mejor calidad de cielos Shinkai. Úsalo si Nano Banana no da la estética que buscas en los fondos. `--cref` para consistencia de personaje.
- **Krea.ai** o **Leonardo.ai** (backup gratis): si agotas cuota de Nano Banana.

## Reglas de consistencia (aplican a TODAS las generaciones)

1. Aspect ratio: **9:16** (para todo). En Midjourney: `--ar 9:16 --style raw`. En Nano Banana: especificarlo en el prompt: `vertical 9:16 composition`.
2. Estilo: **Makoto Shinkai / CoMix Wave** siempre en el prompt.
3. Época: **19th century European seaside** o `19th century interior` siempre.
4. Iluminación: **warm golden hour, volumetric light** siempre.
5. Grano: `subtle film grain` para textura Shinkai.
6. Negativos (si la herramienta los acepta): `no modern objects, no phones, no cars, no plastic, no photorealism, no 3D render look, no cel-shading harsh lines`.

---

## PASO 0 — Character Reference Sheets (bloqueante)

Antes de tocar cualquier frame, generar 3 hojas de referencia. Cada hoja: **3 vistas del mismo personaje (frontal, 3/4, perfil), fondo neutro claro, misma iluminación**. Estas hojas se cargan como referencia en los frames posteriores.

### Sheet 1 — Rocío

**Prompt (Nano Banana o Midjourney):**
```
Character reference sheet, anime style Makoto Shinkai aesthetic, young woman around 25 years old, warm brown skin, shoulder-length wavy black hair with soft side-swept bangs framing the face, thin rectangular black-framed glasses, dark almond-shaped eyes, gentle warm smile, slender build, wearing a dark charcoal fitted vest over a white high-collared blouse, three views in one image: front view, three-quarter view, side profile, all views on a soft neutral cream background, consistent lighting warm golden hour, subtle film grain, vertical 9:16 composition. No photorealism.
```

Iterar hasta que las 3 vistas se vean como la misma persona. Descargar como `rocio_ref.png`.

### Sheet 2 — Orión

**Prompt:**
```
Character reference sheet, anime style Makoto Shinkai aesthetic, young man around 27 years old, warm brown skin, short black natural hair with a soft forehead fringe falling slightly over one eyebrow, thin rectangular black-framed glasses, expressive dark eyes, warm gentle smile with slight teeth visible, defined but soft jawline, medium build, notably shorter fingers, wearing a light cream loose linen shirt, three views in one image: front view, three-quarter view, side profile, all views on a soft neutral cream background, consistent lighting warm golden hour, subtle film grain, vertical 9:16 composition. No photorealism.
```

Descargar como `orion_ref.png`.

### Sheet 3 — Jazmín

**Prompt:**
```
Character reference sheet, anime style Makoto Shinkai aesthetic, young woman around 24 years old, luminous light brown skin, very long straight black hair flowing past shoulders, no glasses, deep dark obsidian eyes, serene contained warm smile, delicate elegant features, slender graceful build, wearing a simple long flowing pale coral dress, three views in one image: front view, three-quarter view, side profile, all views on a soft neutral cream background, consistent lighting warm golden hour, subtle film grain, vertical 9:16 composition. No photorealism.
```

Descargar como `jazmin_ref.png`.

**Verificación paso 0:**
- [ ] `rocio_ref.png` — mismas gafas, mismo largo de cabello, misma piel en 3 vistas
- [ ] `orion_ref.png` — misma cara, mismo pelo, misma camisa
- [ ] `jazmin_ref.png` — mismo pelo largo, misma piel, mismo vestido

Si alguna vista no cuadra: regenerar con seed diferente, o pedir a la herramienta "keep same character, redraw side view".

---

## PASO 1 — Frame 1 (sanity check, sin cara)

Este es el frame más fácil (manos sobre teclas, cero cara). Sirve para verificar que la estética Shinkai sale bien antes de meter personajes.

**Prompt:**
```
Anime style Makoto Shinkai aesthetic, extreme close-up shot of a young man's hands on the yellowed ivory keys of an old upright piano, notably shorter fingers, one finger trembling very faintly (subtle motion blur on that finger only), warm afternoon golden hour light spilling from a side window on the right, dust particles floating in the light beam, aged wooden piano with subtle scratches, 19th century interior background softly out of focus, cinematic shallow depth of field, subtle film grain, melancholic mood, vertical 9:16 composition. No photorealism, no modern objects.
```

Verificación:
- [ ] Se ve estética Shinkai (cielo/luz volumétrica no necesario aquí, pero sí calidez)
- [ ] Piano vertical (upright) no de cola
- [ ] Teclas amarillentas (no blancas frescas)
- [ ] Cero elementos modernos

Si sale bien, sabemos que el estilo está locked. Guardar como `frame_01.png`.

---

## PASO 2-13 — Frames restantes

Para cada frame, si involucra personaje, **cargar la hoja de referencia correspondiente** en Nano Banana (subir imagen + escribir prompt). En Midjourney usar `--cref URL_DE_LA_HOJA --cw 100`.

### Frame 2 — Rocío reflejo en ventana (usa `rocio_ref.png`)
```
Anime style Makoto Shinkai aesthetic, the woman from the reference image, seen from behind, standing very still facing a tall arched window with wooden frame, her partial reflection visible on the glass showing a single tear on her right cheek, outside the window a 19th century European seaside village at afternoon golden hour with gray clouds turning amber, dust particles in the interior light, warm interior tones vs cool exterior sky contrast, muted melancholy, subtle film grain, vertical 9:16 composition.
```

### Frame 3 — Té sobre mesa (usa `rocio_ref.png`)
```
Anime style Makoto Shinkai aesthetic, overhead close-up of a delicate white porcelain teacup steaming on an aged dark wooden table, the woman from the reference image partially visible from above only her brown-skinned hands, one hand carefully placing the teacup down while the other hand trembles very faintly in the corner of the frame, warm afternoon sunlight from side window creating soft shadows, 19th century interior, tender melancholy, subtle film grain, vertical 9:16 composition. No photorealism.
```

### Frame 4 — Orión al piano ojos cerrados (usa `orion_ref.png`)
```
Anime style Makoto Shinkai aesthetic, the man from the reference image playing an old upright piano with his eyes closed and brow furrowed in emotion, seated on a wooden stool, seen from a slight side angle, an open tall window behind him revealing a dramatic Shinkai-style sunset sky in tones of gray, amber, and deep red, silhouette of a 19th century European seaside village visible in the distance through the window, warm interior lighting contrasting with the sunset, melancholic cinematic composition, subtle film grain, vertical 9:16.
```

### Frame 5 — Rocío silueta con maletas (usa `rocio_ref.png`)
```
Anime style Makoto Shinkai aesthetic, silhouette of the woman from the reference image standing in the center of a warm 19th century interior room, two large brown leather suitcases with brass buckles at her feet, strongly backlit by a large arched window showing a golden Shinkai-style sunset outside, her posture upright but resigned, dust motes floating in the sunbeam, warm amber palette, high-contrast silhouette, melancholic composition, subtle film grain, vertical 9:16.
```

### Frame 6 — Puerta con cerradura antigua
```
Anime style Makoto Shinkai aesthetic, extreme close-up of an antique brass door lock and handle on a heavy dark wooden door with visible grain and iron nails, camera slightly tilted with an implied motion vibration from a knock, warm interior lighting from the left creating dramatic shadows on the wood, 19th century European craftsmanship, tense composition, subtle film grain, vertical 9:16 composition. No modern hardware.
```

### Frame 7 — Ojos cruzados triple (usa `rocio_ref.png` y `orion_ref.png`)

Este es en realidad TRES imágenes que se combinan verticalmente en CapCut. Generar cada una:

**7a — Ojos de Orión:**
```
Anime style Makoto Shinkai aesthetic, extreme close-up of the man from the reference image's dark almond eyes, looking sideways to the right with an expression of anguish and helplessness, thin rectangular glasses in frame, warm golden hour lighting reflected in his pupils, subtle film grain, horizontal composition to be cropped later.
```

**7b — Ojos de Rocío:**
```
Anime style Makoto Shinkai aesthetic, extreme close-up of the woman from the reference image's dark almond eyes behind thin rectangular glasses, downcast with a single unshed tear glistening on the lower lash, warm golden hour lighting, subtle film grain, horizontal composition to be cropped later.
```

**7c — Puerta entreabierta:**
```
Anime style Makoto Shinkai aesthetic, medium close-up of a heavy dark wooden door slightly ajar, warm outdoor light spilling in through the crack in a golden ray, dust particles visible in the light beam, 19th century interior, tense expectation, subtle film grain, horizontal composition to be cropped later.
```

Los tres se apilan verticalmente en CapCut en el segundo 24-29.

### Frame 8 — Rocío caminando por madera (usa `rocio_ref.png`)
```
Anime style Makoto Shinkai aesthetic, low camera angle at floor level, only the hem of a long simple dark charcoal dress and dark leather shoes of the woman from the reference image moving slowly across an aged wooden plank floor with visible grain and scratches, warm afternoon light streaming diagonally from the left, dust motes in the light beam, 19th century interior, sense of reluctant heavy motion, melancholic, subtle film grain, vertical 9:16 composition.
```

### Frame 9 — Té en el aire slow motion (usa `orion_ref.png`)
```
Anime style Makoto Shinkai aesthetic, dynamic action shot, the man from the reference image caught mid-fall having just tripped over a small wooden table, his body angled forward with hands reaching out, a white porcelain teacup and its amber liquid suspended in mid-air in slow motion around him, some of the tea already splashed onto his light cream shirt creating a wet stain, 19th century interior warm afternoon light, dust particles disturbed by the motion, urgency and helplessness in his expression, cinematic composition, subtle film grain, vertical 9:16.
```

### Frame 10 — Mano al hombro (usa `rocio_ref.png` + `orion_ref.png`)
```
Anime style Makoto Shinkai aesthetic, back view close-up of the woman from reference image 1 with wavy black shoulder-length hair and thin rectangular glasses, her right hand reaching for an antique brass door handle, the man from reference image 2's right hand from behind reaching her left shoulder just barely making contact, both figures frozen in the exact moment of contact, warm 19th century interior lighting, unbearable emotional tension, subtle film grain, vertical 9:16 composition.
```

### Frame 11 — Miradas cruzadas + freeze (usa `rocio_ref.png` + `orion_ref.png`)

Split composition (dos imágenes que van en pantalla dividida en CapCut). Generar cada una:

**11a — Ojos de Rocío girando:**
```
Anime style Makoto Shinkai aesthetic, extreme close-up of the woman from the reference image's dark almond eyes behind thin rectangular glasses, turning sideways to the right, a single crystalline tear caught mid-fall on her right cheek, expression of deep sorrow, warm interior light reflected in her pupils, subtle film grain, horizontal composition to be cropped.
```

**11b — Ojos de Orión al suelo:**
```
Anime style Makoto Shinkai aesthetic, extreme close-up of the man from the reference image's dark almond eyes looking down at a wooden plank floor, unable to meet her gaze, shame and heartbreak in expression, thin rectangular glasses in frame, warm interior light, subtle film grain, horizontal composition to be cropped.
```

### Frame 12 — Freeze frame + texto
Es el mismo Frame 11 combinado. El texto se añade en CapCut, no en la generación.

### Frame 13 — Logo Bitácora + La Estancia
No es generación IA. Diseñar en CapCut o Canva:
- Fondo negro absoluto
- Título superior: **BITÁCORA** — tipografía serif elegante (recomiendo Cormorant Garamond o Playfair Display), color hueso #F5F0E8, tamaño grande
- Subtítulo debajo: **· La Estancia ·** — misma tipografía, menor tamaño, cursiva
- Debajo del subtítulo, tipografía sans-serif ligera: *"Serie completa. Cada domingo. Link en bio."*
- Fade in de 1.5s, mantener 0.5s

---

## Orden de trabajo recomendado (día por día, plan B)

**Día 1 (heavy — ~4h):**
- Paso 0: 3 character reference sheets (iterar hasta que salgan)
- Paso 1: Frame 1 (piano hands sanity check)

**Día 2 (heavy — ~4h):**
- Frames 2, 3, 4, 5

**Día 3 (heavy — ~4h):**
- Frames 6, 7 (3 sub-imágenes), 8

**Día 4 (heavy — ~3h):**
- Frames 9, 10, 11 (2 sub-imágenes), 12, 13

**Día 5 (~3h):** Animación en Kling 3.0

**Día 6 (~2h):** Música Udio + voz ElevenLabs

**Día 7 (~3h):** Edición CapCut + publicación

**Total 1ra semana: ~19h.** Después de esto, 2h/semana es viable para ep 1-3.

---

## Nota crítica sobre iteración

No aceptes el primer render. Cada frame regenera **mínimo 3 veces** y quédate con el mejor. Especialmente:

- **Ojos**: Nano Banana a veces distorsiona ojos en close-up. Si salen raros, regenerar con seed distinta.
- **Gafas**: fáciles de perder o cambiar de forma. Verificar consistencia con la hoja de referencia.
- **Fondos**: si el fondo Shinkai sale plano, añadir al prompt `dramatic cloud formations, layered sky in gradient tones, cinematic depth`.
- **Colores**: si sale muy saturado, añadir `desaturated palette, restrained color, muted tones`.

## Cuando hayas terminado

Notifícame. Reviso los 13 frames + 3 hojas de referencia. Ajustamos los que no cuadren antes de animar en Kling (animar un frame que no funciona = créditos desperdiciados).
