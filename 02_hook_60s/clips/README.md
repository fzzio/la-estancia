# Fase 2 — Animación Kling 3.0

Prompts para animar los 13 frames del hook en Kling 3.0 (klingai.com).

## UI Kling 3.0 (VIP)

Cada archivo `NN_*.txt` incluye bloque `========== KLING 3.0 SETTINGS ==========` con los valores exactos a poner en la UI:

- **Mode**: `1080p` (VIP — pagado). Alternativas: 720p (free), 4K (VIP).
- **Length**: slider **entero de 3s a 15s** (snaps a valores enteros: 3, 4, 5, 6, 7... — NO acepta decimales). Se usa el timeline slot redondeado hacia arriba, el excedente se trima en CapCut.
- **Video Ratio**: `9:16` (OBLIGATORIO — default UI es 16:9, HAY QUE CAMBIARLO cada vez).
- **Number of Outputs**: 1 (default) / 2-4 (VIP). Sugerido: 1 en la mayoría, 2 solo en clips críticos donde vale gastar créditos extra (créditos son limitados aunque seas VIP).
- **Native Audio**: OFF (audio va aparte en ElevenLabs/Udio, no queremos que Kling meta ruido).
- **Multi-Shot**: OFF (single clip, no queremos escenas encadenadas).
- **Negative Prompt**: Kling 3.0 **NO tiene campo separado**. Se anexa dentro del mismo prompt como `Avoid: ...` al final.
- **Camera Control**: Kling 3.0 UI **NO tiene campo separado**. La instrucción de cámara (static / push-in / pull-out / tracking) va DENTRO del prompt principal en inglés.

## Tabla duración por clip

| Clip | Timeline slot | Kling Length | CapCut Post |
|------|---------------|--------------|-------------|
| 1A/B/C | 0.8+1.2+0.5s | **3s** c/u (mínimo, triptych) | trim c/u a slot |
| 2  | 3.5s | **4s** (slider entero, no 3.5s) | trim 0.5s |
| 3  | 5.0s | **5s** | ninguno ✅ |
| 4  | 5.0s | **5s** | ninguno ✅ |
| 5  | 4.0s | **4s** | ninguno ✅ |
| 6  | 4.0s | **4s** | ninguno ✅ |
| 7A/B/C | 1.7s c/u | **3s** c/u (mínimo) | trim 1.3s c/u |
| 8  | 5.0s | **5s** | ninguno ✅ |
| 9  | 7.0s | **7s** | ninguno (sin slow-mo artificial) ✅ |
| 10 | 5.0s | **5s** | ninguno ✅ |
| 11A/B | 7.0s c/u | **7s** c/u | ninguno ✅ |
| 12 | 5.0s | NO Kling | CapCut still + typewriter text |
| 13 | 2.0s | NO Kling (recomendado) | CapCut still + fade + micro-shake |

## Outputs recomendados por clip

Créditos VIP son limitados; ir conservador:
- **2 outputs**: clips 1, 4, 7A, 8, 9, 10, 11A, 11B (motion complejo o beats críticos — vale gastar el doble para elegir)
- **1 output**: clips 2, 3, 5, 6, 7B, 7C, 13 (motion simple/estático — si sale mal, regeneras solo ese)

## Reglas de estilo

- Motion prompts en inglés (Kling entiende mejor).
- Cada prompt termina con `Avoid: ...` que reemplaza el negative prompt inexistente en 3.0.
- Movimiento sutil y contenido. Este hook gana con quietud, no con acción exagerada.
- Preservar estilo Shinkai — Kling 3.0 tiende a suavizar el trazo anime; si sale más realista, regenerar con "keep 2D anime cel-shaded aesthetic" reforzado.

## Orden de generación sugerido

Con VIP y 2 outputs máximo en clips críticos, no hay throttling significativo. Orden lazy:
1. **Empezar por clip 1** (apertura, el más re-generable si sale mal).
2. Clips 2-6 en serie (motion simple).
3. Clip 7 triptych (3 mini-clips).
4. Clip 8 (deceleración compleja).
5. **Clip 9 último** (pico visual, quieres los 4 outputs para elegir).
6. Clip 10, 11A, 11B en serie.
7. Frame 13 pendiente → generar en Nano Banana antes de decidir opción A/B del clip 13.

## Frame 13 pendiente

El logo (`frame_13.png`) todavía no está generado. Cuando lo tengas, evaluar si se anima en Kling (opción A) o solo CapCut (opción B, recomendado). Prompt listo en `13_logo.txt`.

## Enriquecimiento por motivos literarios (2026-07-29)

Los clips 1, 3, 4, 7A, 8 y 10 fueron enriquecidos con motivos específicos del PDF original ("La estancia") para reforzar la sensación buscada más allá del beat básico:

- **Clip 1**: micro-gesto de mano al pecho izquierdo (motif de dolor de Parte I)
- **Clip 3**: té tibio (no caliente), ceremonia ritual de vieja receta (Parte II)
- **Clip 4**: ira contenida + dinámica fuerte-suave del piano (Parte I "fuerte y oscura")
- **Clip 7A**: máscara emocional que cae cuando ella no lo ve (Parte III, beat literario clave)
- **Clip 8**: pasos progresivamente más lentos como sobre brasas (Parte III)
- **Clip 10**: gap de 2-3mm entre mano de Rocío y la perilla + cabeza gacha de Orión (Partes III-IV)

Cada uno incluye una sección `========== LITERARY MOTIF ==========` al final que explica el pasaje. **NO pegar esta sección en Kling** — es contexto para ti, no para la IA. Si Kling no interpreta bien la instrucción compleja del motion prompt, quita descripciones adjetivas ("aching", "ceremonial") y deja solo la coreografía técnica.
