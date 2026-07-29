# Fase 2 — Animación Kling 3.0

Prompts para animar los 13 frames del hook en Kling 3.0 (klingai.com).

## Configuración global para todos los clips

- **Modelo**: Kling 3.0 (o 3.1 si disponible)
- **Modo**: Standard suele bastar. Pro solo si Standard sale con artifacts (recomendado probar Standard primero para conservar créditos).
- **Aspect ratio**: 9:16 vertical **OBLIGATORIO** en TODOS los clips.
- **Duración**: usar la que indica cada archivo. Kling free tier suele topar 5s. Los clips que piden 7s (9 y 11) se resuelven así:
  - Opción A: generar en Kling 5s + ralentizar final en CapCut (0.7x) para llegar a 7s
  - Opción B: si tienes créditos, usar modo Pro que permite 10s
- **First frame**: subir el PNG correspondiente de `assets/frames_output/`.
- **Last frame (opcional)**: la mayoría no lo necesita. Cuando sí, se indica en el archivo.
- **Camera control**: Kling 3.0 tiene control de cámara (push in, pull out, pan, tilt, static). Se indica en cada prompt.

## Reglas de estilo

- Motion prompts en inglés (Kling entiende mejor).
- Movimiento sutil y contenido. Este hook gana con quietud, no con acción exagerada.
- Preservar estilo Shinkai — Kling 3.0 tiende a suavizar el trazo anime; si sale más realista, regenerar con "keep 2D anime cel-shaded aesthetic" reforzado.
- Negative prompt siempre incluye: distorted anatomy, morphing faces, unnatural motion, photorealism, 3D CGI.

## Estrategia créditos

Kling free ~66 créditos/día. Standard 5s ≈ 10 créditos. 13 clips × 10 = 130 créditos → **necesitas ~2 días o pagar Pro**. Prioriza generar en orden 1→13. Si te quedas sin créditos, guarda progreso y sigues al día siguiente.

## Frame 13 pendiente

El logo (`frame_13.png`) todavía no está generado. Cuando lo tengas, el clip 13 se anima con un fade in simple (2s). Prompt ya listo en `13_logo.txt` de este folder — solo esperando la imagen base.
