---
name: outsider-art-v1
description: "Transform a user-supplied photo (semantic reference only) or a text theme into a dense, flat, naïve Outsider Art poster: a map-like mixed-projection world built from large flat color zones, each zone carrying one uniform hand-made texture (window dot-grids, stitch dashes, woven riso grain, ink contour), populated by tiny solid-silhouette faceless figures (never stick figures) doing ordinary things. Every image uses paper white, warm ink black, and a narrow set of 2–4 subdued scene-derived zone colors, plus exactly ONE saturated highlight color (any hue) doing real compositional work. Use whenever the user wants this folk-art / faux-naïf / risograph poster look, mentions Outsider Art, 织纹海报, flattened aerial scenes, tiny crowds, or asks to render a place, memory, season, or list of moments in this style — with a photo or from words alone."
---

# Outsider Art v1.2

Create a calm, dense, flat poster in a naïve folk-art print language. Preserve the five signature principles:

- **世界是平摊的 / The world lies flat:** naïve mixed projection — ground planes read as tilted map-like color zones seen from above, while trees, people, buildings, and vehicles stand upright in flat elevation. No vanishing point, no converging lines, no 3D.
- **密纹成静 / Repetition makes quiet:** calm comes from dense, even, hand-made texture — not from blank minimalism. Abstraction works by miniaturizing, not by omitting.
- **色窄成静 / The palette stays narrow:** each image uses paper white, warm ink black, and only 2–4 subdued, inky zone colors chosen for that scene's season, time, and place. Dense fields stay quiet because the colors stay few and muted.
- **一枚亮色 / One highlight:** exactly one saturated color per image — any hue, freshly chosen for the scene — the only high-chroma color anywhere, and it always has a compositional job.
- **人是刻度 / People are the scale:** tiny faceless figures doing ordinary things give the scene size, rhythm, and warmth.

Two input modes share one pipeline:

- **Photo mode:** the photo is a **semantic reference only**. Extract place, activities, spatial bands, native palette, and mood; never retain, trace, crop, or embed photographic pixels or photorealistic regions.
- **Theme mode:** no photo; invent the scene from the user's words.

Return the generated image plus one brief creative rationale in Chinese. Include the final prompt only when the user explicitly asks.

## Decision Priority

Resolve conflicts in this order:

1. Preserve the flattened naïve mixed projection; never introduce linear perspective, 3D depth, lighting, or shadows.
2. Keep the color structure: narrow subdued zone palette + exactly one saturated highlight; no second high-chroma system.
3. Build the canvas from a few large flat color zones, each carrying exactly one uniform texture system.
4. Achieve calm through even repetition and narrow color; densify before you empty.
5. Populate with tiny faceless figures whose activities fit the scene.
6. Give the highlight one clear role (focal object OR structural line color) and make it earn its place.
7. Choose one composition family and one edge treatment; do not blend them.
8. Keep the theme legible: a viewer should name the kind of place or idea without a caption.
9. Default to no text.

Miniaturize before omitting. Repeat before decorating.

## Consent and Source Handling

- A supplied photo plus a request to transform or generate is consent to use image generation; do not ask again.
- Use the photo for semantic analysis only. Send only the final prompt and required reference image to the generation service.
- Do not browse, search, save, upload elsewhere, or share the user's source material.
- Generalize identifiable faces, plates, and signs; this style never renders likeness anyway.
- Do not save source or generated images into project files unless the user asks.

## Build the Field Card

Inspect the input before composing. Resolve every field:

- **Place kind:** park, waterfront, street, campus, beach, market, courtyard, rooftop view, or an abstract theme (a season, a list of moments, a collection).
- **Band inventory:** the 2–5 large zones the world divides into — road, path, lawn, water, sand, plaza, building mass, sky-as-paper. Note their real order and rough proportions.
- **Native palette:** the scene's season, time of day, climate, and materials, and the subdued hues they imply (photo mode: read them from the photo; theme mode: derive them from the world of the theme).
- **Population:** what people are doing here — walking, cycling, dog-walking, sitting, reading, playing, swimming, waiting. Choose 2–5 activities.
- **Cast objects:** trees (note species character: palm, broadleaf, bare winter branches), benches, cars, boats, bicycles, kites, umbrellas — the small props that tell the place.
- **Highlight candidates:** the scene-embedded elements that could deserve the one saturated color — a building, a car, a garment, an awning, a boat, a door, a fruit, a sign — or a linear system (trunks + path edges, a lift line, kite strings) if the scene is line-led. List at least two candidates before choosing.
- **Dominant gesture:** the strongest diagonal, band direction, promenade line, or shoreline.
- **Density profile:** which zones want dense texture (city mass, water, crowd) and which stay plainer (lawn, paper sky).
- **Orientation:** portrait or landscape energy.
- **Mood:** default is unhurried everyday public life, observed from a friendly distance.

**Photo mode:** fill the card from what the photo shows, then discard the photo's composition, perspective, light, and pixels entirely. Keep only the card.
**Theme mode:** fill the card by invention; ground every invented item in the stated theme.

## Composition Director

### Canvas

- Portrait **2:3** by default; use landscape **3:2** when the source photo or the described scene is clearly horizontal (shoreline, promenade, panorama). Square or ambiguous input defaults to portrait.
- The image is a flat printed poster: matte paper surface, even riso/screen-print grain, orthographic flat light, no mockup framing.

### Choose ONE composition family

- **Layered Zones（分层地带）:** the world stacks as 2–5 horizontal or gently diagonal flat color bands — e.g., dark road / paper promenade / green lawn / deep water. Space is geology, not perspective. Bands may tilt 5–20° for movement. Use for any continuous real place. This is the default.
- **Specimen Scatter（图鉴散点）:** elements float on open paper like a catalog page — trees of different species, a person on a bench, a bicycle, a dog — each drawn separately, no shared ground, no unified projection. One side may carry a torn paper band in a zone color. Use when the input is a collection, an inventory of moments, a list, a taxonomy, or when the user asks for it.

Supporting technique for Layered Zones — **Density Collision（密度对撞）:** press an extremely dense textured mass (packed building windows, crowded water, thick foliage) directly against a plain flat zone. The contrast is the drama; do not soften the boundary with gradient or haze.

### Layout rules

- 2–5 zones only. One zone should dominate (roughly 35–60% of the canvas); no accidental 50/50 splits.
- Align band edges with the Field Card's dominant gesture (shoreline, promenade, road).
- In Layered Zones, texture and figures cover most of the canvas; open paper appears only as its own deliberate zone (a paper-white sky or promenade), never as leftover margin.
- In Specimen Scatter, paper is the ground: keep roughly 40–65% open paper, scatter 6–14 specimens with uneven spacing, varied size, and no grid alignment.
- Establish one eye path: enter through the largest zone or the scatter's densest corner, meet the highlight, travel along the dominant gesture, exit through a quieter band.

## Projection Rules — the fragile core

State these explicitly in every prompt; generation models will otherwise "correct" them away:

- Ground zones are seen from above, flattened like a hand-drawn map.
- Trees, people, buildings, vehicles, and props stand upright in simple flat elevation (side or front view) on those zones, like a child's drawing or a folk map.
- No vanishing point, no converging lines, no foreshortening, no horizon atmosphere.
- Distance may be shown only by gentle size reduction and higher placement on the canvas.
- Nothing casts a shadow. Light is even and directionless.

## Texture Grammar

Every color zone carries **exactly one** texture system, uniform in rhythm and density across that zone:

- **Window dot-grid:** tiny rectangular/dot window arrays for building masses; each façade a slightly different hand-drawn grid.
- **Stitch dashes:** short parallel dashes or hand ticks for water, grass, pavement; direction follows the zone's flow.
- **Woven riso grain:** an overall fabric-like screen-print grain that can sit under the whole image, strongest in Layered Zones posters.
- **Foliage scribble mass:** dense looped/ticked canopy blobs for tree crowns — canopies are FILLED dark masses, never line-only fronds or skeleton outlines; trunks are single confident lines. Line-only trees are allowed solely for bare winter branches.
- **Pure ink contour:** clean wobbly hand line for figures, vehicles, benches, props; minimal interior detail.

Rules:

- Never mix two texture systems inside one zone; never let texture density wander within a zone.
- Texture is hand-made and slightly irregular in stroke, but even in overall rhythm — dense fields must read as calm fabric at thumbnail size, not as noise.
- All texture is opaque flat ink on paper: no gradients, no transparency ramps, no painterly blending.
- **Knockout rule:** when a dark object (tree, figure, cabin) sits on a dark zone, a thin paper-white knockout outline is allowed — it is honest print separation. Never put white outlines around objects on light zones; that reads as sticker clipping.

## Color System

### Fixed anchors (every image)

- **Paper white:** warm off-white paper with visible grain; also usable as a zone color (sky, promenade, snow, sand).
- **Ink black:** warm near-black for all contours, figures, window grids, and dark zones (night road, asphalt).

### Zone Palette Decision (per image)

Beyond the anchors, choose **2–4 subdued zone colors** freshly for each image:

- Derive them from the Field Card's native palette: season, time of day, climate, materials. An October coast, a winter night, a summer pool, and a brick courtyard should NOT share one palette.
- Keep every zone color low-to-mid chroma, inky, print-like — the register of deep bottle green, sage, prussian navy, charcoal indigo, warm grey-brown, ochre-khaki, dusty brick, slate blue, deep olive.
- Keep the set narrow: related or neighbouring hues telling one color story. Never a rainbow; never two competing color stories in one image.
- Name each color exactly in the prompt ("deep olive green", "charcoal indigo", "warm ochre-khaki") — never just "green" or "blue".
- A subdued neutral (grey-brown / khaki / straw) is a normal citizen of this system for baskets, kerbs, props, and earth zones.
- One optional tiny prop tint (e.g., pale sky-blue for car windows, glass jars, goggles, water glints) may appear at very small total area; it must stay clearly quieter than the highlight.

### Highlight Engine

Exactly **one saturated highlight color** per image — the only high-chroma color anywhere. It may be any hue: vermilion, tomato red, marigold, cobalt, kingfisher blue, magenta, chartreuse — whatever the scene earns.

Resolve a **Color Decision** before choosing:

- **Role:** focal pin, counterweight, bridge between zones, or directional cue.
- **Relation to the zone palette:** temperature counterpoint, focused complement, intensified native minor color, or a stronger analogous hue.
- **Value and chroma:** how it must separate from paper, ink, and every zone color at thumbnail size.
- **Material form and area:** flat printed shape or thin line system.

Then choose **one role** per image:

- **Focal object:** one highlighted thing the scene is quietly about — the one bright tower in a pale city, the bright car on a dark road, the bright coat on a lawn, an awning among plain stalls. Area roughly **1–6%** of the canvas. One or two much smaller echoes allowed; together below a third of the main accent's area.
- **Structural line color:** the highlight replaces ink for one linear system — a lift line with its towers and cabins, tree trunks plus path edges, a railing network, kite strings. Total area roughly **3–10%**, always thin lines over a large reach, never a filled mass. No separate highlighted focal object in this role.

Rules:

- State the exact color name; never weaken it with pale, muted, faded, pastel, or low-saturation wording.
- **Never choose a hue or a motif merely because an example, a reference image, or a previous generation used it.** In particular, a sun or moon disc in the corner of the sky is a lazy default: prefer a highlight embedded in the scene (garment, awning, vehicle, boat, door, fruit, sign, stall). A sky disc is allowed only when the time of day is itself the subject of the request.
- Removal test: mentally delete the highlight. If the eye path, balance, and the scene's small story survive unchanged, it is decoration — redesign it. Never place the highlight as an arbitrary swatch, corner block, or border.

## Figure System

- **Figures are small solid silhouettes, never stick figures.** Each figure is built from a few compact FILLED flat shapes — a solid torso wearing a flat clothing color, limbs with visible width, a solid blob or dot head. Wire-thin line limbs and outline-circle heads (matchstick people) are a hard failure of the style.
- Figures are tiny by default: roughly **1.5–5%** of canvas height each, each made of 3–7 filled flat shapes.
- **Close-up register:** only when the user explicitly asks for a close-up, street-level, or few-figure scene — 1–5 figures at roughly **8–15%** of canvas height, 5–12 filled flat shapes, still faceless. Never enter this register on your own judgement.
- **No facial features, ever.** Heads are solid blank dots or simple filled shapes; identity comes from posture and activity. Headwear, goggles, and helmets are allowed as simple flat color patches; eyes, noses, and mouths are not.
- Draw them mid-activity from the Field Card: walking with a bag, pedaling, throwing a ball, sitting reading, leading a dog. Stiff, earnest, faux-naïf — never cute, never chibi, never cartoon-proportioned.
- Scatter 3–20 figures in Layered Zones (fewer in empty-feeling scenes, more on busy promenades) with uneven spacing and varied direction; 1–4 in Specimen Scatter.
- Clothing is flat opaque fills from the zone palette and anchors; at most one figure wears the highlight (and only when the highlight's role is focal object).

## Edge Treatment

Choose one:

- **Full bleed:** zones run off every edge. Default for Layered Zones.
- **Torn side band:** one vertical torn-paper strip in a deep zone color along a single side, fibrous tear against the paper. Default companion for Specimen Scatter; usable in Layered Zones.
- **Drawn frame:** a hand-drawn double-line ink border with a sparse leaf or tick pattern in the margin. Use when the poster wants a woven-rug or storybook-plate feeling.

Never combine treatments; never add drop shadows, curled corners, or mockup depth.

## Text Policy

**Default: no text at all.** The canonical works are wordless; silence is part of the style.

Only when the user supplies exact wording: reproduce it verbatim, hand-lettered in ink black (or the highlight only if its role is structural line), small (≤3% of canvas height), placed inside a uniform texture zone or on open paper, aligned to a band edge. Never add titles, dates, logos, signatures, or invented captions on your own.

## Prompt Compiler

Compile only instructions that can become visible pixels. Write the final prompt as four compact paragraphs:

1. **Canvas and world:** ratio, flat poster/riso print nature, composition family, the 2–5 zones with their named colors and rough shares, dominant gesture, eye path, edge treatment.
2. **Projection:** the full Projection Rules, stated as hard constraints.
3. **Inhabitants and textures:** each zone's single texture system; trees/props with species character; figure register, count, size range, activities, blank faces, and the explicit demand for solid filled silhouettes with flat clothing colors — state "never stick figures"; the highlight's exact color, role, form, position, and approximate area.
4. **Palette, mood, and hard avoids:** the named anchors + zone colors as a closed list ("no other hues; the [exact highlight] is the only saturated color"), even flat light, matte paper grain, unhurried everyday mood, and the prohibited aesthetics below.

In photo mode always include: `The supplied photo is a semantic reference only. Do not reproduce, trace, crop, collage, or retain photographic pixels or photorealistic regions. The final image contains original flat illustration only.`

Use decisive language. Say which perspective habits must NOT appear as clearly as what must.

## Generation Workflow

1. Inspect the input; enter photo mode or theme mode.
2. Build the Field Card, including native palette and at least two highlight candidates.
3. Choose orientation (2:3 / 3:2) from the source or scene energy.
4. Choose the composition family; plan the zones, shares, and dominant gesture; decide whether Density Collision applies.
5. Run the Zone Palette Decision: name the 2–4 subdued zone colors.
6. Assign one texture system to each zone.
7. Cast the figures: register (default unless close-up explicitly requested), count, activities, placement rhythm.
8. Run the Highlight Engine: Color Decision, role, exact color, form, position, area; apply the removal test and the anti-default rules.
9. Choose the edge treatment.
10. Apply the Text Policy (almost always: none).
11. Compile the four-paragraph prompt.
12. Generate (with the photo as semantic reference in photo mode).
13. Inspect at normal and thumbnail scale.
14. Regenerate at most once with a targeted correction if needed.
15. Return the image plus one brief Chinese rationale.

## Targeted Correction

Regenerate at most once, fixing only the observed failure:

- **Perspective creep:** re-flatten — restate map-plane ground + elevation objects, remove converging lines, shadows, horizon haze.
- **Palette drift:** zone colors wandered wide, a rainbow appeared, or a second saturated color system emerged — re-narrow to the named closed list.
- **Highlight cliché:** the highlight landed as a default corner sun/moon or copied an earlier image — re-embed it in a scene object or line system.
- **Highlight multiplied:** collapse saturated color back to one system within its role's area budget.
- **Texture noise:** make each zone's texture uniform in rhythm; remove mixed systems and density wobble.
- **Figures wrong:** refill stick figures as solid clothed silhouettes, shrink figures that exceed their register, erase facial features, stiffen cartoon cuteness into naïf earnestness.
- **Line-art drift:** the whole image thinned into etching-like line work — refill figure bodies, tree canopies, and props' color patches as solid flat shapes.
- **Too empty:** densify the dominant zones; this style fails by sparseness, not by fullness.
- **Zone mush:** restore hard flat boundaries between zones; remove blends and soft transitions.
- **Photo leakage (photo mode):** remove photographic texture or realism; redraw as flat ink illustration.
- **Theme illegible:** restore the Field Card's place-telling props and activities.

## Hard Avoids

Avoid linear perspective, vanishing points, foreshortening, horizon haze, atmospheric depth, 3D rendering, cast shadows, soft shadows, gradients, glossy vector cleanliness, painterly brushwork, watercolor bleeds, photographic pixels or textures, photorealistic regions, cinematic lighting, depth of field, facial features on figures, stick figures, matchstick or wire-limbed line-only figures, likeness of real people, cute cartoon / kawaii / anime / chibi proportions, children's-book sweetness, a second saturated color system, rainbow or candy palettes, pastel palettes, default corner sun/moon discs, hues or motifs copied from examples or previous generations, neon, sparse white minimalism in Layered Zones, uneven or mixed textures within a zone, white sticker outlines on light zones, decorative borders beyond the three edge treatments, drop shadows, curled paper, mockups, unrequested text, titles, dates, signatures, logos, CTA, and watermarks.

## Output Format

By default, return:

```markdown
![Outsider Art poster](absolute-image-path-or-rendered-image)

**创作思路**

[One short Chinese paragraph: the zones the world was flattened into, the color story chosen for this scene, what the tiny people are doing, and the job the single highlight is performing.]
```

Keep the rationale to 1–3 sentences. Do not reveal the full prompt or restate parameters unless the user explicitly asks; on request, notes may use:

- Field Card: [place kind / bands / native palette / population / highlight candidates]
- Composition: [family / zones and shares / gesture / edge]
- Palette: [anchors + named zone colors]
- Textures: [zone → texture system]
- Highlight: [exact color / role / form / approximate area]
- Figures: [register / count / activities / size range]

## Quality Gate

Before returning, verify:

- Does the ground read as flat map-like zones with upright elevation objects — no perspective anywhere?
- Are there 2–5 zones with one dominant, hard boundaries, and one texture system each?
- Does every dense field read as calm even fabric at thumbnail size?
- Are the zone colors 2–4, subdued, narrow, scene-derived, and exactly named — one color story, no rainbow?
- Is there exactly one saturated color, and is it the highlight?
- Does the highlight pass the removal test, within its role's area budget, embedded in the scene rather than defaulting to a corner sky disc or a hue copied from an example?
- Are the figures solid filled silhouettes with flat clothing — never stick figures — in the correct register (tiny by default), faceless, mid-activity, and naïf rather than cute?
- Is the composition family pure (no half-scatter half-zones hybrid)?
- Is the edge treatment single and clean, with knockout outlines only on dark zones?
- In photo mode, is the result 100% original illustration with zero photographic material?
- Is the poster wordless unless the user supplied exact text?
- Can a viewer name the kind of place or idea without a caption?
- Did the response include the image and one genuinely brief Chinese rationale, with the prompt withheld unless requested?
