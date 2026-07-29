# Bitácora — La Estancia

Estructura del proyecto para copiar prompts limpios y retomar en cualquier sesión.

## Rutas rápidas

- **Plan completo del hook 60s**: `../hook_60s_plan.md` (concepto, música, edición, criterios de éxito)
- **Character bible**: `../character_bible_la_estancia.md` (rasgos abstractos anime de los 3 personajes)
- **Estado actual del proyecto**: `PROGRESS.md`

## Cómo usar

Cada prompt vive en su propio `.txt`. Copia el contenido completo del archivo y pégalo en la herramienta indicada. No edites el prompt sin razón. Si necesitas iterar, guarda variantes como `frame_XX_v2.txt`.

## Orden de trabajo (bloqueante — no saltarse)

1. `01_character_sheets/` — 3 hojas de referencia (Rocío, Orión, Jazmín) generadas y descargadas a `assets/refs/`
2. `02_hook_60s/frames/` — 14 prompts de frames del hook, ejecutar en orden 01 → 11b
3. `02_hook_60s/voz_off_es.txt` + `voz_off_en.txt` — generar en ElevenLabs
4. `02_hook_60s/musica_udio.txt` — generar en Udio
5. Animación (Kling 3.0) + Edición (CapCut) — instrucciones en `../hook_60s_plan.md`

## Herramientas

- **Krea.ai** (principal para frames): https://krea.ai — free tier suficiente para pilot. Mejor calidad anime Shinkai puro que Nano Banana. Configurar aspect ratio a 9:16 antes de generar. NUNCA mencionar Ghibli en prompts (deriva estética indeseada).
- **Nano Banana** (backup / character sheets ya generados): https://aistudio.google.com/ → usar `gemini-3.1-flash-image` (NO la versión `-lite`, sigue instrucciones anatómicas mal). Solo usar para regenerar character sheets o frames simples.
- **Midjourney** (opcional, $10/mes): `--ar 9:16 --style raw --cref URL`
- **Kling 3.0**: https://klingai.com para animación
- **Udio**: https://udio.com para música
- **ElevenLabs**: https://elevenlabs.io voces Adam o Antoni
- **CapCut**: edición final vertical 9:16

## Lecciones aprendidas (actualizar aquí conforme avancemos)

- **2026-07-28**: `gemini-flash-lite-image` sigue pobre las instrucciones anatómicas. Usar versión full o cambiar a Krea.
- **2026-07-28**: Krea.ai free supera a Nano Banana en estilo Shinkai/Ghibli. Recomendado como principal para frames de escena. Verificar aspect ratio 9:16 en settings de Krea (no viene por default).

## Regla crítica de estilo anime (aprendida en frame 01)

Nano Banana (gemini-2.5-flash-image) sesga a fotorrealismo. Las negativas solas NO bastan. Cada prompt debe:

1. **Afirmar el estilo explícitamente** al inicio: `2D anime illustration, hand-drawn cel-shaded animation, Makoto Shinkai film aesthetic`
2. **Repetir "anime" varias veces** en el prompt (al menos 3 menciones)
3. **Describir el estilo de dibujo**: "clean line art, flat colors with soft gradients, cel shading"
4. **Negar fotorrealismo explícitamente**: `NOT photorealistic, NOT 3D render, NOT CGI, NOT live action, NOT DSLR photograph`
5. **Referencias específicas de películas Shinkai**: "Your Name", "5 Centimeters per Second", "Weathering with You"

Si un render sale fotorrealista → regenerar con anime enforcement reforzado o cambiar a otra herramienta (Krea.ai / Midjourney tienden más al anime).

## Regla crítica de piel (paleta)

Tonos neutros para compatibilidad con audiencia masiva anime. Gradiente entre los 3:
- **Rocío**: soft warm ivory con matices olivo (tono ancla)
- **Orión**: light warm ivory con matices dorados (similar a Rocío, ligeramente más neutro)
- **Jazmín**: porcelana pálida con matices peach, casi translúcida (la más clara — encaja con su calidad etérea de "ángel encarnado")

Ninguno debe salir con piel oscura tostada tipo "warm brown".

## Regla crítica de vestuario

Los character sheets deben mostrar **vestuario siglo XIX europeo completo**, no solo cara. Si un render sale con pants, jeans, botines modernos, sneakers, o cualquier ropa post-1900: **regenerar**. El sheet no es solo referencia facial — es referencia de personaje completo con vestuario de época locked.

Verificar en cada sheet:
- Rocío: falda larga al piso + chaleco + blusa cuello alto + cadena de reloj + botines de cuero
- Orión: camisa de lino crema cuello mandarín + chaleco + pantalón de tiro alto + botines
- Jazmín: vestido largo talle imperio coral, mangas abullonadas, encaje marfil

## Personajes

| Personaje | Rol | Ref file |
|---|---|---|
| Rocío | Relojera | `01_character_sheets/rocio.txt` |
| Orión | Pianista | `01_character_sheets/orion.txt` |
| Jazmín | Nueva visita (aparece ep 10) | `01_character_sheets/jazmin.txt` |

## Assets locales

Guardar imágenes generadas en:
- `assets/refs/` — hojas de referencia de personajes
- `assets/frames_output/` — frames finales del hook

Nombrar `rocio_ref.png`, `orion_ref.png`, `jazmin_ref.png`, `frame_01.png` ... `frame_13.png`.
