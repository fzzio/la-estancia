# Progreso generación Kling — Hook 60s La Estancia

Registro por clip: metadata Kling, review contra prompt, decisión (aceptar / regenerar / mantener como B-roll).

Ubicación de clips generados: `assets/clips_output/NN_nombre.mp4`

---

## Clip 01 — REDISEÑADO como TRIPTYCH (2026-07-30)
- **Estado**: 🔄 Prompt reescrito, pendiente generar 01A/01B/01C
- **Motivo del cambio**: Kling no ejecuta cortes editoriales dentro de un solo clip. La cámara se queda fija en las manos y el gesto al pecho se pierde fuera de frame (verificado en 2 regeneraciones consecutivas).
- **Nueva estructura**: 3 mini-generaciones separadas + montaje CapCut
  - **01A**: extreme close-up manos piano (0.8s)
  - **01B**: medium shot 3/4 frontal torso, mano al pecho (1.2s) — TOMA CLAVE
  - **01C**: extreme close-up ojos flicker (0.5s)
- **Frames Nano Banana**:
  - ⚠️ `frame_01b.png` v1 generado 2026-07-30 — pose 3/4 correcta pero sonrisa leve + falta corbatín negro del bible. Prompt refinado en `frames/01b_orion_chest.txt` (2026-07-30). Regenerar con nuevas reglas: expresión CALM sin sonrisa + corbatín negro visible + edge-to-edge sin bordes.
  - ⚠️ `frame_01c.png` v1 generado 2026-07-30 — ojos correctos pero picture-within-picture (wood panels arriba/abajo). Prompt refinado en `frames/01c_orion_eyes_pain.txt` (2026-07-30) con FRAMING RULE crítica: full-frame edge-to-edge macro portrait, glasses tocan bordes L/R, hair top edge, nose bottom edge. Regenerar.
- **Prompt actualizado**: `clips/01_piano_hands.txt`

**Clips previos generados** (archivar como B-roll o descartar):
- `01_piano_hands.mp4` (2026-07-30 07:23) — framing incorrecto, sin gesto
- Regeneración posterior — mismo problema, gesto fuera de frame

---

## Clip 02 — Rocío reflejo ventana
- **Estado**: ✅ APROBADO (post-trim)
- **Archivo**: `assets/clips_output/02_rocio_window.mp4`
- **Metadata**: 4.04s, 1076x1924 (9:16), 24fps, h264 ✓
- **Fecha generación**: 2026-07-30 09:33
- **Settings usados**: 4s, 9:16, 1080p

**Cumple prompt:**
- Rocío de espaldas frente a ventana ✓
- Reflejo visible en cristal ✓
- Lágrima cristalina en reflejo aparece progresivamente (frame 04) ✓
- Body/hair estáticos ✓
- Cielo sunset Shinkai ✓
- Camera static ✓
- Cel-shaded ✓

**Verificaciones bible:**
- Pelo largo (aquí llega casi a cintura) vs bible "wavy shoulder-length" → ⚠️ verificar contra character bible antes de flagear. Puede ser que shoulder-length + wavy caiga hasta esta longitud en anime.

**CapCut post**: trim 0.5s (donde la lágrima aún no aparece — segundos 0-0.5).

---

## Clip 03 — Té sobre mesa
- **Estado**: ⚠️ REVIEW — framing incorrecto
- **Archivo**: `assets/clips_output/03_tea_cup.mp4`
- **Metadata**: 5.04s, 1076x1924 (9:16), 24fps, h264 ✓
- **Fecha generación**: 2026-07-30 09:55
- **Settings usados**: 5s, 9:16, 1080p

**Cumple prompt:**
- Estilo Shinkai ✓
- Té ámbar con vapor sutil (no exagerado) ✓
- Reloj de bolsillo con cadena dorada visible ✓ (motif del pocket watch)
- Mesa madera envejecida ✓
- Luz cálida dorada ✓
- Motion mínimo (mano se retira) ✓

**Falla prompt:**
- ❌ **Framing incorrecto**: prompt pide "overhead top-down close-up". Clip entrega ángulo tres cuartos lateral, con perspectiva casi frontal. Se ve la mesa desde arriba pero no top-down puro.
- ⚠️ Al segundo 2 solo queda una mano en el frame (no dos como pedía prompt: una en handle + otra con cloth ajustando cup)
- ⚠️ Tremor en ring finger no visible

**Veredicto pendiente**: decidir si:
- (a) Regenerar con "STRICT top-down 90-degree overhead angle, camera directly above the table looking straight down"
- (b) Aceptar este framing (más cinematográfico) y ajustar continuidad del hook

---

## Pendientes generar
- Clip 04 — Orión piano ojos cerrados (5s, 2 outputs)
- Clip 05 — Rocío silueta maletas (4s, 1 output)
- Clip 06 — Puerta cerradura (4s, 1 output)
- Clip 07A/B/C — Triptych ojos (3s×3)
- Clip 08 — Rocío camina (5s, 2 outputs)
- Clip 09 — Té slow motion (7s, 2 outputs) — PICO VISUAL
- Clip 10 — Mano al hombro (5s, 2 outputs)
- Clip 11A/B — Ojos girando (7s×2, 2 outputs cada uno)
- Clip 13 — Logo (frame_13.png pendiente en Nano Banana)

Clips 12 y 13 (opción B) se resuelven en CapCut sin Kling.

---

## Notas de aprendizaje

- Kling 3.0 tiende a interpretar "close-up" como "medium shot with detail". Reforzar con "fills 90% of frame + background out-of-focus bokeh only" para forzar intimidad.
- El motion básico se ejecuta bien. Los micro-gestos coreografiados (mano al pecho segundo 2, tremor específico) se pierden con frecuencia.
- Camera control dentro del prompt funciona pero Kling no siempre respeta (clip 01 push-in casi no se percibe, clip 03 no es overhead).
- Considerar generar 2 outputs en cualquier clip con framing complejo, no solo en críticos.
