---
name: adaptive-chibi-avatar-skill
description: Generate 1:1 hand-painted chibi portrait avatars from a reference image, with selectable illustration style and a 0–1 realism control. Use for Q版头像, 手绘人物头像, or style-specific chibi portraits.
---

# Adaptive Chibi Avatar

Create a square, head-and-shoulders avatar from a reference image. Keep the person or character recognisable through their face silhouette, hairstyle, facial hair, headwear, key accessories, and dominant clothing shapes. The result is an illustration, never a photo or a generic anime face.

If no reference is available, create an original character only; do not claim likeness.

## Inputs

- `style`: one of the standard styles below. Default: `watercolor-sketch`.
- `realism`: a number from `0.0` to `1.0`. Default: `0.7`.
- `expression`: a short, reference-specific description of the eyes, brows, mouth, gaze, head angle, and—only if essential—one hand gesture.

Translate a natural-language style request to the closest standard style. Use one style only unless the user explicitly asks for a blend.

## Non-negotiable output rules

- Make a 1:1 square avatar. Use a close head-and-shoulders crop; the head occupies about 70–80% of the canvas height, with small shoulders or upper chest visible.
- Keep a clearly chibi silhouette at every realism level: enlarge and round the head, make the cheeks slightly fuller, shorten the lower face, and make the eyes modestly larger than the source while preserving their shape and spacing. Avoid infant-like proportions and oversized glossy anime eyes.
- Preserve the source's identifying visual features. Simplify minor facial planes and incidental skin detail instead of replacing the face.
- Render skin as designed illustration colour, not as a literal copy of poor lighting or camera white balance. Preserve the subject's complexion and its range of lightness; do not arbitrarily lighten it. Remove muddy yellow, grey, or underexposed colour casts when they come from the source lighting, then use clean, balanced midtones and gentle value changes.
- Keep outlines fine to medium and irregular. Use dark ink mainly for facial cues and small separations; let colour and value define most outer edges. Outer contours must be broken, pale, or colour-tinted rather than continuous black edges. Never use a thick, uniform black border around the head, body, clothing, or accessories.
- Keep the background simple and supportive: use paper texture or a low-detail colour field, plus 3–7 small, style-matched washes, dry-brush marks, ink speckles, or grain accents around the outer silhouette. Keep these accents out of the face and below 15% of the canvas; scenery, UI, poster framing, borders, and busy props are not allowed.
- Do not generate text, letters, numerals, captions, signatures, logos, or watermarks.
- If an important source prop contains writing—for example a banknote, card, screen, book, label, or sign—either omit it or render it as a blank, unmarked shape.

## Realism control

Treat `realism` as a visual-detail dial, not a guarantee of photographic accuracy.

| Range | Result |
| --- | --- |
| `0.0–0.35` | Strong Q version: broad simplification, smooth graphic skin, almost no wrinkles, pores, or fine texture. |
| `0.36–0.65` | Stylised portrait: clear likeness with smooth painted skin and limited soft facial detail. |
| `0.66–0.80` | Default range: clear likeness with an obvious Q silhouette; skin is made from broad, smooth blended colour regions with simplified facial planes, no pores, no paper grain or individual tool marks, and at most a few soft expression lines. |
| `0.81–1.0` | Detailed illustrated portrait: retain more reference-specific skin texture and expression lines, but remain visibly painted rather than photographic. |

At every level, include skin texture only when it helps the reference-specific likeness. Do not invent wrinkles, pores, blemishes, or weathered skin. At `0.66–0.80`, keep brush, paper, pencil, and print texture in the hair, clothing, and background; do not put it in facial skin.

## Standard styles

| `style` | Direction |
| --- | --- |
| `watercolor-sketch` | Transparent washes, dry-brush texture, and light broken grey-brown or colour-tinted pencil marks; airy, never black-outlined. |
| `gouache-marker` | Opaque, matte colour blocks, small dry-brush highlights, clean handmade finish. |
| `ink-wash` | Expressive ink values and watery washes, mostly monochrome with an optional restrained accent colour. |
| `oil-paint` | Visible layered brushstrokes, rich but controlled colour, soft painted light; avoid photo-like skin. |
| `colored-pencil` | Fine coloured-pencil grain, layered strokes, paper showing through. |
| `soft-pastel` | Matte, velvety colour transitions with powdery texture and soft edges. |
| `editorial-flat` | Simplified graphic shapes, limited palette, subtle printed texture, no heavy outlines. |
| `comic-ink` | Lively thin ink lines, restrained hatching, clear colour blocks; never thick contour bands. |
| `risograph` | Limited offset-print palette, visible grain and slight registration texture, simple shapes. |

## Prompt template

Start with this English prompt. Replace the brackets and append a concise expression add-on.

```text
Transform the subject in the reference image into a [STYLE] hand-painted chibi portrait avatar. Preserve their recognisable face silhouette, hairstyle, facial hair, headwear, key accessories, and dominant clothing shapes. Do not replace them with a generic anime face.

Create a 1:1 square close head-and-shoulders composition. The head occupies about 70–80% of the image height, with small shoulders or upper chest visible. Keep a clearly chibi silhouette: round the head, make the cheeks slightly fuller, shorten the lower face, and make the eyes modestly larger than the source while preserving their shape and spacing. Avoid baby proportions and huge glossy anime eyes.

Use exactly the visual language of [STYLE]. Keep the portrait visibly illustrated. Apply realism level [REALISM] according to the realism-control rules: [REALISM DIRECTION]. For realism `0.66–0.80`, render facial skin as broad, smooth blended colour regions with no visible pores, paper grain, or individual brush, pencil, or print marks; place the selected medium's texture in the hair, clothing, and background instead. Preserve the subject's complexion without mechanically copying muddy yellow, grey, or underexposed lighting casts; use clean, balanced illustrated skin midtones and gentle value changes.

Use fine-to-medium, irregular dark lines only for facial cues and small separations. Define most outer edges through paint value and colour. Keep outer contours broken, pale, or colour-tinted rather than continuous black edges. No thick, uniform black outlines or black contour bands.

Use a simple paper-texture or low-detail colour-field background, with 3–7 small [STYLE]-matched washes, dry-brush marks, ink speckles, or grain accents around the outer silhouette. Keep those accents out of the face and below 15% of the canvas. No scenery, text, letters, numerals, captions, signatures, logos, watermarks, UI, poster layout, borders, or frames. If a source prop contains writing, omit it or make it a blank unmarked shape.

Avoid photorealism, 3D rendering, plastic skin, beauty-filter effects, smooth digital airbrush, generic anime faces, heavy black outlines, dense black shading, detailed scenery, and unrelated props.

EXPRESSION ADD-ON: [REFERENCE-SPECIFIC EXPRESSION]
```

Write `REALISM DIRECTION` from the matching range above. For `EXPRESSION ADD-ON`, state only the visible eyes, brows, mouth, gaze, head angle, and one essential gesture if needed; do not add a smile or gesture that the reference does not support.
