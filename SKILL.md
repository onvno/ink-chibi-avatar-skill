---
name: vivid-chibi-avatar-skill
description: Generate high-saturation, hand-painted chibi avatars from a reference image, with a close face crop, smooth skin, thin expressive ink, and composed red-blue ink splashes. Use for Q版头像, 手绘卡通头像, or high-contrast chibi portraits.
---

# Vivid Ink-Splash Chibi Avatar

Create one fixed illustration style: a vivid hand-painted chibi avatar with a prominent face, smooth opaque skin colour, lively fine ink, and an intentional red-and-blue ink-splash composition. Preserve the subject's recognisable face silhouette, hairstyle, facial hair, headwear, key accessories, and dominant clothing shapes. Do not replace the subject with a generic anime face or a photo-like painted portrait.

If no reference is available, create an original character only; do not claim likeness.

## Inputs

- `realism`: a number from `0.0` to `1.0`. Default: `0.7`.
- `expression`: a short, reference-specific description of the eyes, brows, mouth, gaze, and head angle. Add one hand gesture only when it is essential.

`realism` controls how much reference-specific facial shape and expression is retained. It does not allow pores, facial grain, or photorealistic skin.

| Range | Result |
| --- | --- |
| `0.0–0.45` | Strong Q version: broad, playful facial simplification and very few facial details. |
| `0.46–0.69` | Stylised chibi portrait: clear likeness with smooth, simplified facial planes. |
| `0.70–0.80` | Default range: mature, recognisable Q portrait with accurate expression and smooth, low-detail skin. |
| `0.81–1.0` | More reference-specific facial structure and expression lines, while remaining visibly illustrated and free of pores or photographic skin texture. |

## Fixed visual rules

- Create a 1:1 close head-and-shoulders avatar. The head occupies about 78–85% of the canvas height. Keep the face as the clear focal point; show only enough shoulders or upper chest to identify clothing.
- Make the head rounded and enlarged, the cheeks subtly fuller, and the lower face slightly shorter. Keep adult character traits; avoid infant proportions and huge glossy anime eyes.
- Use rich, clean, high-contrast colour. Preserve the subject's complexion and its lightness range, but remove muddy yellow, grey, underexposed, or coloured-light casts from the source. Use warm, lively skin midtones, controlled warm shadows, clear cheek and lip colour, dark hair or clothing anchors, and crisp light clothing highlights where the source supports them.
- Render facial skin as broad, opaque, smoothly blended colour regions. Do not show pores, paper grain, stippling, pencil scratches, dry-brush marks, random specks, blemishes, or noisy micro-texture on the face. Put paint texture in the hair, clothing, and background instead.
- Use fine-to-medium irregular ink only for brows, eyes, nostrils, mouth, hair separations, clothing folds, and small overlap points. Outer contours must be broken or varied; never use a thick, uniform black border around the head, body, clothing, or accessories.
- Use a warm off-white paper background. Add one deliberate, asymmetric red-and-blue ink-splash composition behind and around the outer silhouette: two or three connected focal pools, tapered wet-brush flicks, a few radial filaments, and sparse satellite droplets. Let the composition echo the curve and energy of the head and shoulders; leave the face and its immediate edge clean. Do not scatter equal-sized dots randomly or turn the background into a scene.
- Do not generate text, letters, numerals, captions, signatures, logos, watermarks, UI, poster layouts, borders, frames, or unrelated props. If a source prop contains writing, omit it or render it as a blank shape.

## Prompt template

Start with this English prompt. Replace the brackets and append a concise expression add-on.

```text
Transform the subject in the reference image into a vivid hand-painted chibi portrait avatar. Preserve the subject's recognisable face silhouette, hairstyle, facial hair, headwear, key accessories, and dominant clothing shapes. Do not substitute a generic anime face or a photo-like painted portrait.

Create a 1:1 close head-and-shoulders avatar. The head occupies about 78–85% of the canvas height; keep the face as the unmistakable focal point, with only enough shoulders or upper chest to identify clothing. Keep a clear adult chibi silhouette: round enlarged head, subtly fuller cheeks, shortened lower face, and eyes modestly larger than the source while retaining their shape and spacing. Avoid baby proportions and huge glossy anime eyes.

Apply realism level [REALISM]: [REALISM DIRECTION]. Use rich, clean, high-contrast colour. Preserve the subject's complexion and its lightness range, but correct muddy yellow, grey, underexposed, or coloured-light casts from the source. Use warm lively skin midtones, controlled warm shadows, clear cheek and lip colour, dark hair or clothing anchors, and crisp light clothing highlights where supported by the source.

Render facial skin as broad, opaque, smoothly blended colour regions. No pores, paper grain, stippling, pencil scratches, dry-brush marks, random specks, blemishes, or noisy micro-texture on the face. Put paint texture in the hair, clothing, and background instead.

Use fine-to-medium irregular ink only for brows, eyes, nostrils, mouth, hair separations, clothing folds, and small overlap points. Keep outer contours broken or varied; no thick uniform black border or black contour band.

Use a warm off-white paper background. Add one deliberate asymmetric red-and-blue ink-splash composition behind and around the outer silhouette: two or three connected focal pools, tapered wet-brush flicks, a few radial filaments, and sparse satellite droplets. Let it echo the curve and energy of the head and shoulders, while keeping the face and its immediate edge clean. Do not use random equal-sized dots, detailed scenery, text, logos, watermarks, UI, poster layouts, borders, or frames.

EXPRESSION ADD-ON: [REFERENCE-SPECIFIC EXPRESSION]
```

For `EXPRESSION ADD-ON`, describe only the visible eyes, brows, mouth, gaze, head angle, and one essential gesture if needed. Do not add a smile or gesture that the reference does not support.
