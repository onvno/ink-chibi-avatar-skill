---
name: vivid-chibi-avatar-skill
description: Generate high-saturation, hand-painted chibi avatars from a reference image, with a close face crop, smooth skin, thin expressive ink, and subtle palette-matched paint splashes. Use for Q版头像, 手绘卡通头像, or high-contrast chibi portraits.
---

# Vivid Accent-Splash Chibi Avatar

Create one fixed illustration style: a vivid hand-painted chibi avatar with a prominent face, smooth opaque skin colour, lively fine ink, and subtle palette-matched paint splashes. Preserve the subject's recognisable face silhouette, hairstyle, facial hair, headwear, key accessories, and dominant clothing shapes. Do not replace the subject with a generic anime face or a photo-like painted portrait.

If no reference is available, create an original character only; do not claim likeness.

## Inputs

- `realism`: a number from `0.0` to `1.0`. Default: `0.5`.
- `expression`: a short, reference-specific description of the eyes, brows, mouth, gaze, and head angle. Add one hand gesture only when it is essential.
- `face-shape`: optional. Use `subtle` by default; use `wider`, `longer`, or a user-provided custom direction only when the user explicitly requests that exaggeration.

`realism` controls how much reference-specific facial structure is retained. It does not allow pores, facial grain, or photorealistic skin. At the default `0.5`, preserve the subject through a few high-signal anchors—hair, brows, gaze, mouth, facial hair, and key costume shapes—not exact adult facial geometry.

| Range | Result |
| --- | --- |
| `0.0–0.45` | Strong Q version: broad, playful facial simplification and very few facial details. |
| `0.46–0.59` | Default range: clear expression with a deliberately redesigned Q face—large open eyes, fuller cheeks, a shorter lower face, and smooth broad colour planes. |
| `0.60–0.80` | Likeness-forward Q portrait: preserve more facial structure and expression while remaining visibly caricatured. |
| `0.81–1.0` | More reference-specific facial structure and expression lines, while remaining visibly illustrated and free of pores or photographic skin texture. |

## Fixed visual rules

- Create a 1:1 close head-and-shoulders avatar. The head occupies about 80–86% of the canvas height. Keep the face as the clear focal point; show only enough shoulders or upper chest to identify clothing.
- Make the head rounded and enlarged, the cheeks fuller, and the lower face clearly shorter. At the default `0.5`, use a deliberate Q redesign: eyes about one-quarter larger and more open than the source, with visible sclera that carries the reference-specific gaze; make the nose and mouth smaller and simpler; do not preserve exact jaw, chin, or skin-crease geometry. Preserve eye shape, spacing, iris character, and adult traits. `face-shape: subtle` means no additional width or length distortion beyond these default Q proportions; apply a wider, longer, or other exaggeration only when `face-shape` explicitly requests it. Avoid infant proportions and huge glossy anime eyes.
- Use rich, clean, high-contrast colour. Preserve the subject's complexion and its lightness range, but remove muddy yellow, grey, underexposed, or coloured-light casts from the source. Use warm, lively skin midtones, controlled warm shadows, clear cheek and lip colour, dark hair or clothing anchors, and crisp light clothing highlights where the source supports them.
- Render facial skin as broad, opaque, smoothly blended colour regions. Do not show pores, paper grain, stippling, pencil scratches, dry-brush marks, random specks, blemishes, or noisy micro-texture on the face. Put paint texture in the hair, clothing, and background instead.
- Use fine-to-medium irregular ink only for brows, eyes, nostrils, mouth, hair separations, clothing folds, and small overlap points. Outer contours must be broken or varied; never use a thick, uniform black border around the head, body, clothing, or accessories.
- Preserve a few reference-specific flyaway locks beyond the hair silhouette, using loose tapered ink strokes that follow the hair flow. Keep them intentional and airy, not a dense tangled outline.
- Use a warm off-white paper background. Add a restrained, palette-matched paint accent behind the outer silhouette: one small, light translucent splash cluster with a few tapered flicks and sparse satellite droplets. Add two or three very faint, broken dry-brush or ink arcs around the outer hair silhouette as an incomplete hand-drawn halo. Derive one or two softened accent colours from the subject's clothing, hair, accessories, or the user's palette request; do not default to red and blue. Keep all background marks below 8% of the canvas, leave the face and its immediate edge clean, and preserve generous negative space. Do not scatter equal-sized dots randomly or turn the background into a scene.
- Do not generate text, letters, numerals, captions, signatures, logos, watermarks, UI, poster layouts, borders, frames, or unrelated props. If a source prop contains writing, omit it or render it as a blank shape.

## Prompt template

Start with this English prompt. Replace the brackets and append a concise expression add-on.

```text
Transform the subject in the reference image into a vivid hand-painted chibi portrait avatar. Preserve high-signal identity anchors: hairstyle, brows, gaze, mouth, facial hair, headwear, key accessories, and dominant clothing shapes. Do not reproduce exact adult facial geometry, substitute a generic anime face, or make a photo-like painted portrait.

Create a 1:1 close head-and-shoulders avatar. The head occupies about 80–86% of the canvas height; keep the face as the unmistakable focal point, with only enough shoulders or upper chest to identify clothing. Keep a clear adult chibi silhouette: round enlarged head, fuller cheeks, clearly shortened lower face, and eyes about one-quarter larger and more open than the source, with enough visible sclera to carry the reference-specific gaze while retaining eye shape, spacing, and iris character. At realism `0.5`, make the nose and mouth smaller and simpler and do not retain exact jaw, chin, or skin-crease geometry. `subtle` means no additional width or length distortion beyond these default Q proportions. Apply [FACE-SHAPE DIRECTION] only when the user explicitly requests it. Avoid baby proportions and huge glossy anime eyes.

Apply realism level [REALISM]: [REALISM DIRECTION]. Use rich, clean, high-contrast colour. Preserve the subject's complexion and its lightness range, but correct muddy yellow, grey, underexposed, or coloured-light casts from the source. Use warm lively skin midtones, controlled warm shadows, clear cheek and lip colour, dark hair or clothing anchors, and crisp light clothing highlights where supported by the source.

Render facial skin as broad, opaque, smoothly blended colour regions. No pores, paper grain, stippling, pencil scratches, dry-brush marks, random specks, blemishes, or noisy micro-texture on the face. Put paint texture in the hair, clothing, and background instead.

Use fine-to-medium irregular ink only for brows, eyes, nostrils, mouth, hair separations, clothing folds, and small overlap points. Keep outer contours broken or varied; no thick uniform black border or black contour band.

Preserve a few reference-specific flyaway locks beyond the hair silhouette, using loose tapered ink strokes that follow the hair flow; keep them intentional and airy, not a dense tangled outline.

Use a warm off-white paper background. Add one small, light translucent paint-splash accent behind the outer silhouette, with a few tapered flicks and sparse satellite droplets. Add two or three very faint broken dry-brush or ink arcs around the outer hair silhouette as an incomplete hand-drawn halo. Derive one or two softened accent colours from the subject's clothing, hair, accessories, or a user-supplied palette when present; do not default to red and blue. Keep all background marks below 8% of the canvas, leave the face and its immediate edge clean, and preserve generous negative space. Do not use random equal-sized dots, detailed scenery, text, logos, watermarks, UI, poster layouts, borders, or frames.

EXPRESSION ADD-ON: [REFERENCE-SPECIFIC EXPRESSION]
```

For `FACE-SHAPE DIRECTION`, use `subtle` unless the user explicitly asks for a wider, longer, or custom facial proportion. For `EXPRESSION ADD-ON`, describe only the visible eyes, brows, mouth, gaze, head angle, and one essential gesture if needed. Do not add a smile or gesture that the reference does not support.
