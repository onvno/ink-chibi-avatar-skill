---
name: ink-wash-chibi-avatar-skill
description: Generate 1:1 Chinese ink-wash chibi avatars from a reference image, with enlarged expressive eyes, smooth skin, flowing ink hair, and restrained rice-paper accents. Use for 水墨 Q版头像, 国风卡通头像, or ink-painted chibi portraits.
---

# Ink-Wash Chibi Avatar

Create one fixed illustration style: a lively Chinese ink-wash chibi avatar on warm rice paper. Preserve the subject through high-signal identity anchors—hairstyle, brows, gaze, mouth, facial hair, headwear, key accessories, and dominant clothing shapes—rather than exact adult facial geometry. The result must be clearly hand-painted and Q versioned, never a realistic ink portrait or generic anime face.

If no reference is available, create an original character only; do not claim likeness.

## Inputs

- `realism`: a number from `0.0` to `1.0`. Default: `0.5`.
- `expression`: a short, reference-specific description of the eyes, brows, mouth, gaze, and head angle. Add one hand gesture only when it is essential.
- `face-shape`: optional. Use `subtle` by default; use `wider`, `longer`, or a user-provided custom direction only when the user explicitly requests that exaggeration.

At the default `0.5`, preserve the subject through a few identity anchors and their emotional expression—not through exact adult face geometry.

| Range | Result |
| --- | --- |
| `0.0–0.45` | Strong Q version: broad, playful facial simplification and very few face details. |
| `0.46–0.59` | Default range: clear expression with a deliberately redesigned Q face—large open eyes, fuller cheeks, shorter lower face, and smooth ink-wash colour planes. |
| `0.60–0.80` | Likeness-forward Q portrait: preserve more facial structure and expression while remaining visibly caricatured. |
| `0.81–1.0` | More reference-specific facial structure and expression lines, while remaining ink-painted and free of pores or photographic skin texture. |

## Fixed visual rules

- Create a 1:1 close head-and-shoulders avatar. The head occupies about 80–86% of the canvas height. Keep the face as the clear focal point; show only enough shoulders or upper chest to identify clothing.
- Use a deliberate adult Q redesign: rounded enlarged head, fuller cheeks, clearly shorter lower face, and eyes about one-quarter larger and more open than the source. Show enough sclera to carry the reference-specific gaze while preserving eye shape, spacing, and iris character. Make the nose and mouth smaller and simpler. `face-shape: subtle` means no additional width or length distortion beyond these default Q proportions. Avoid infant proportions and huge glossy anime eyes.
- Paint with deep charcoal black and warm grey, plus clean, high-chroma fluid ink washes. Select one or two colour inks that suit the reference—such as cinnabar, vermilion, rich ochre, indigo, jade, or violet—and use them for lively but brush-led contrast. Keep the water-ink character through translucent wash edges and visible brush flow, not flat digital colour blocks or glossy shading.
- Render facial skin as smooth, opaque ink-wash colour planes. Preserve the subject's complexion range while using clear warm or cool undertones, lively cheek and lip colour when supported by the reference, and distinct light-to-shadow contrast. Do not show pores, paper grain, stippling, pencil scratches, dry-brush marks, random specks, blemishes, or noisy micro-texture on the face. Reserve wet and dry brush texture for hair, facial hair, clothing, and background.
- Use fine-to-medium calligraphic ink strokes for brows, eyes, nostrils, mouth, hair separations, facial hair, clothing folds, and overlap points. Keep contours broken, varied, and sparse; never use a thick uniform black border or dense black shading.
- Preserve a few reference-specific flyaway locks beyond the hair silhouette with tapered wet-and-dry ink strokes that follow the hair flow. Keep them intentional and airy, not tangled.
- Use warm off-white rice paper. Add a small, light but chromatic accent wash behind the outer silhouette, using the chosen colour ink, plus two or three incomplete loose brush arcs around the outer hair silhouette. Keep all background marks below 6% of the canvas, leave the face and its immediate edge clean, and preserve generous negative space. Do not use large paint bursts, random dot fields, or scenery.
- Do not generate text, letters, numerals, captions, signatures, logos, watermarks, UI, poster layouts, borders, frames, or unrelated props. If a source prop contains writing, omit it or render it as a blank shape.

## Prompt template

Start with this English prompt. Replace the brackets and append a concise expression add-on.

```text
Transform the subject in the reference image into a lively Chinese ink-wash chibi portrait avatar. Preserve high-signal identity anchors: hairstyle, brows, gaze, mouth, facial hair, headwear, key accessories, and dominant clothing shapes. Do not reproduce exact adult facial geometry, substitute a generic anime face, or make a realistic ink portrait.

Create a 1:1 close head-and-shoulders avatar. The head occupies about 80–86% of the canvas height; keep the face as the unmistakable focal point, with only enough shoulders or upper chest to identify clothing. Make a deliberate adult Q redesign: a rounded enlarged head, fuller cheeks, clearly shorter lower face, and eyes about one-quarter larger and more open than the source, with enough visible sclera to carry the reference-specific gaze while retaining eye shape, spacing, and iris character. Make the nose and mouth smaller and simpler. `subtle` means no additional width or length distortion beyond these default Q proportions; apply [FACE-SHAPE DIRECTION] only when the user explicitly requests it. Avoid baby proportions and huge glossy anime eyes.

Apply realism level [REALISM]: [REALISM DIRECTION]. Paint with deep charcoal black and warm grey plus clean high-chroma fluid ink washes. Select one or two colour inks that suit the reference—such as cinnabar, vermilion, rich ochre, indigo, jade, or violet—and use them for lively brush-led contrast. Keep translucent wash edges and visible brush flow; no flat digital colour blocks, glossy digital shading, or photorealistic lighting.

Render facial skin as smooth, opaque ink-wash colour planes. Preserve the subject's complexion range while using clear warm or cool undertones, lively cheek and lip colour when supported by the reference, and distinct light-to-shadow contrast. No pores, paper grain, stippling, pencil scratches, dry-brush marks, random specks, blemishes, or noisy micro-texture on the face. Place wet and dry brush texture in the hair, facial hair, clothing, and background instead.

Use fine-to-medium calligraphic ink strokes only for brows, eyes, nostrils, mouth, hair separations, facial hair, clothing folds, and small overlap points. Keep contours broken, varied, and sparse; no thick uniform black borders or dense black shading. Preserve a few reference-specific flyaway locks beyond the hair silhouette with tapered wet-and-dry ink strokes that follow the hair flow.

Use warm off-white rice paper. Add one small light but chromatic accent wash behind the outer silhouette using the chosen colour ink, plus two or three incomplete loose brush arcs around the outer hair silhouette. Keep all background marks below 6% of the canvas, leave the face and its immediate edge clean, and preserve generous negative space. No large paint bursts, random dot fields, scenery, text, letters, numerals, captions, logos, watermarks, UI, poster layouts, borders, or frames.

EXPRESSION ADD-ON: [REFERENCE-SPECIFIC EXPRESSION]
```

For `FACE-SHAPE DIRECTION`, use `subtle` unless the user explicitly asks for a wider, longer, or custom facial proportion. For `EXPRESSION ADD-ON`, describe only the visible eyes, brows, mouth, gaze, head angle, and one essential gesture if needed. Do not add a smile or gesture that the reference does not support.
