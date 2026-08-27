---
name: starlit-relic-v1
description: "Generate (or transform a supplied object photo into) a Starlit Relic image: one isolated object, figurine, model, or figure suspended in a smooth near-black-to-cobalt night gradient with no ground or horizon, lit like a small star with star-filter diffraction spikes, glitter, halation, magenta–cyan chromatic split, and fine analog film grain, on a 3:4 portrait canvas. Use whenever the user mentions 星芒圣物 / starlit relic / 夜空浮物 / 星光滤镜 / 'object floating in a blue night sky with sparkles', wants an object, trophy, crown, animal, building, or player turned into a mythic icon or tribute image, asks for the 'dreamy film sparkle / star filter / GOAT relic' look, or pastes an object photo and asks for 'that blue starry treatment' — even if they never say skill, poster, or style. Do not use for paper-collage, illustration, or daylight photography."
metadata:
  version: "1.4.0"
---

# 星芒圣物 · Starlit Relic v1

一件物体从它的世界里被取出，悬在夜色里，然后被当作一颗星来打光。

Build every image on five fixed principles:

- **一物成像 · One object is the image.** A single subject (or one inseparable group) with no context, no ground, no hands, no stand, no horizon.
- **夜为底色 · Night is the ground.** A smooth vertical gradient from near-black at the top to saturated cobalt at the bottom, covered in fine film grain.
- **光即语法 · Light is the grammar.** The object stays mostly dark; star-filter spikes, glitter, and halation carry all the drama.
- **冷暖对峙 · Warm relic, cold void.** Gold, copper, bronze, and pink-red highlights against ultramarine; flares split into magenta and cyan.
- **胶片实感 · Film physics, not effects.** Grain, halation, chromatic aberration, dust specks — never lens-flare stickers, neon outlines, or 3D-render sheen.

Return the generated image plus one short Chinese creative note (1–3 sentences). Show the final prompt only when the user asks.

The style is fully specified in text — no image references exist or are needed. The canonical frame, held in the mind before composing: *a vertical night of grainy blue, empty of ground and horizon, deepening to near-black at the top; at its optical center, slightly above the middle, one small object hangs weightless and mostly dark — a crown, a hammer, a ship — its metal or stone catching two or three hot points of warm light that burst into thin star-filter spikes fringed magenta on one side and cyan on the other, a soft pink halation bleeding off the brightest point into the blue, everything slightly soft, everything breathing film grain. And when the subject is a person, they stand in that night the way the racer stands on his machine: dusted with particles, wrapped in a quiet cloud, glowing simply in their own color, face free to show.* Read `references/style-anatomy.md` for the per-frame observation records and measured numbers this style was derived from, and `references/prompt-examples.md` for four fully compiled prompts, before writing the first prompt of a session.

## Decision Priority

Resolve conflicts in this order:

1. Keep the relic recognizable as itself at thumbnail size.
2. Keep the void empty: no ground, horizon, second subject, prop, or text.
3. Keep the object mostly dark; let a few hot points do the lighting.
4. Keep the field cool and the relic warm.
5. Make the light behave like film (spikes, halation, chroma split, grain).
6. Place and tilt the object as a suspended, weightless thing.
7. Only then add glitter density, debris, or secondary spikes.

Remove environment before adding light. Add light before adding sparkle count.

## Read the Request First · 圣物卡

Before composing, resolve a **Relic Card**:

- **Relic:** the one object (crown, hoop, figurine, temple, helmet, ship, trophy, sneaker...) or the one inseparable group (three columns, hoop + net).
- **Silhouette test:** the outline that identifies it at thumbnail size; keep it whole.
- **Specular sites:** tips, edges, facets, rims, chains, gems, wet or metallic surfaces — these become the spike and glitter anchors.
- **Material temperature:** gold / bronze / copper / chrome / red enamel / cream stone / dark leather. Decide the warm hue the highlights will carry.
- **Attitude:** how it hangs in the void — level, drifting tilt, falling, rising.
- **Semantic charge (optional):** what the object stands for; let attitude and debris carry it, never captions.
- **Discard list:** stand, base, hands, table, room, sky, real ground, packaging, reflections, other objects.

Input modes:

- **Text concept** ("a floating bronze crown"): invent the object from the Relic Card.
- **Object photo supplied:** treat the photo as an identity reference for the object only. Cut the object free of its environment, keep its shape and material, and re-light it inside the void. Never keep the photo's background, ground, lighting, or crop.
- **Person supplied:** switch to Silhouette Figure or Figure-with-relic grammar (below). Human faces are **never rendered in this style, in any grammar** — a frontal-portrait request is redirected to a strict back view or flat silhouette, with a one-line explanation that facelessness is part of the style, or declined if the user insists. This boundary is enforced at compile time, before any prompt is written.

## Canvas and Field · 画布与夜场

- Canvas: vertical **3:4** by default (the references are 1904×2544). Accept 4:5 or 9:16 only when asked; never landscape unless requested.
- Background is a **single smooth vertical gradient**: the top 25–40% near-black (roughly RGB 10/15/25, faint blue-green cast), easing to saturated cobalt / royal blue at the bottom (roughly RGB 35/75/150 to 45/95/180). No banding, no vignette shapes, no clouds, no stars-as-constellations, no light rays.
- Fine uniform analog film grain over the whole frame, visible in the darks. Add 5–30 faint dust or star specks scattered irregularly (never a starfield).
- Nothing else in the frame: no floor, no horizon line, no reflection, no cast shadow, no smoke, no particles except the object's own companion (see Particle companions). Exception: figure scenes may seal the bottom edge with a pure-black unlit band.

Background variants (choose one):

- **Deep gradient** (default): near-black top → cobalt bottom (crown, wreath).
- **Uniform cobalt:** whole field a lightly graded royal blue; use for smaller, quieter relics (helmet).
- **Day-for-night blue:** a brighter mid royal blue, uniform or gently graded (top ≈ RGB 30/60/100, bottom ≈ 55/110/190), with heavier visible grain — the frame reads like deep daylight sky exposed for night (hammer, longship, colosseum). *Natural fit: the relic is dark, weathered, or large architecture, so it can read as a silhouette against the field.*
- **Inverted:** black top → pale lavender-white bottom; allowed **only** for Silhouette Figure grammar.

Value relationship (decide explicitly, one per image):

- **Lit relic on dark field** (default): the object carries warm highlights brighter than the field.
- **Dark relic on light field:** only with the day-for-night variant; the object sits *darker* than the field as a near-silhouette, and a single hot element carries all the light. The **whole** field must then stay mid-blue — the top edge no darker than ≈ RGB 30/60/100. A near-black top swallows the relic; state this in the prompt as a positive instruction ("the sky stays mid royal blue all the way to the top").

## Subject Placement · 悬置

- Optically centered horizontally: subject center at 45–55% of width.
- Subject center at **40–55% of height** — at or slightly above the geometric center, never in the lower third (large architecture may sit at 38–45%).
- Subject width 25–50% of canvas width; subject height 18–32% of canvas height. Lit area 2–8% of the whole frame. Small relics (helmet, longship) may drop to 20–25% width; a relic cluster may reach 55%; large architecture may reach 60% — and the prompt must state the size share explicitly, because generators inflate architecture.
- Attitude ranges: **Hover** 0–8° tilt; **Drift** 8–20° tilt; **Fall** 25–45° tilt with fragments below; **Rise** 5–15° with spikes trailing downward.
- The object floats. No support, no motion blur, no ground contact.
- The entire silhouette stays inside the frame with at least a 6% margin to every edge; nothing is cropped by the frame. Tall thin relics (torch, sword, oar, column) lean at 8–20° rather than standing vertical — an upright pole meeting the bottom edge reads as planted, not floating.
- The whole silhouette is contained in frame with breathing room — ≥8% margin to every edge; the subject never touches or exits a frame edge (sole exception: the Figure-with-relic foreground band). Objects that normally stand — torches, posts, swords, lamps — do not rise from the bottom edge; they float fully in frame, tilted 8–20°.

Choose one **subject grammar**:

- **Single relic:** one object carries the whole frame (crown, helmet, ship, temple).
- **Relic cluster:** two or three related objects sharing one attitude and one light source (three columns); keep them close, unequal, and slightly staggered.
- **Debris moment:** the object breaks or dissolves; fragments fall below it and turn into sparkle particles; keep 60%+ of the object intact.
- **Figure (alone or with their relic):** a human figure — athlete, driver, monk, dancer — alone or together with the one object or setting that defines them, in the lower or middle half of the frame. **Orientation is free: back, profile, or frontal, and the face may be visible.** What makes it this style is the treatment, not the pose: the figure bathes in particles and drifting dust, wears a simple soft glow of its own dominant color, and stays mostly dark against the night. Optional stylizations when they serve the image: a flat backlit silhouette against a bank of point lights; a near-black close-up where equipment hides most of the face and the eyes carry soft bloom. A pure-black unlit foreground band (5–12% of height) may seal the bottom edge of a figure scene. *The canonical figure frame is the racer on his machine: red suit glowing red, a fountain and a quiet cloud of particles around him, nothing else lit.*

## Light Grammar · 光的语法

One implied hard key light from the upper front, slightly off-axis. Keep **50–70% of the object surface in shadow**; highlights are small, hot, and warm.

These are the style's **light voices**. Every image leads with one dominant voice so the light has a subject, but the voices combine freely — a starburst relic may wear glitter dust, a single flare may trail halation, a glowing figure may stand among spike-lit objects. Let the card's material suggest the lead (guidance, not a lock — and never chosen from keywords in the request; a user who says "sparkly" has not chosen glitter, and a user who says nothing may still need it):

- **Starburst-led:** star-filter diffraction spikes on the specular sites. 4-, 6-, or 8-point; pick one point count per image. 2–6 large primary spikes (length 8–25% of canvas width) plus 10–60 tiny secondary spikes. Each spike shows a **magenta/red fringe on one side and a cyan/blue fringe on the other**. Spikes are thin, straight, and slightly soft — never fat neon rays. *Natural fit: the object has a few discrete hard specular points:* polished metal, gems, tips, rims, chrome, glass, enamel (crown, helmet, trophy, ring, hoop rim).
- **Glitter-led:** the object surface is dusted with hundreds of micro-sparkles so the whole silhouette reads as glowing sand (glitter goat, sparkling net). Sparkles are white-pink; a handful become small spikes. *Natural fit: the surface is continuous fine texture with no single specular point:* fur, plush, suede, mesh, net, knit, sequins, frost, sand, snow, foliage, dense small ornament — or when the whole silhouette must glow rather than a few points.
- **Halation-led:** the hottest points bloom into soft pink-white halos that bleed into the void; edges of the object show faint color fringing. One component of the object may glow like flame or hot metal — a sail, a window row, a crest — while the rest stays dark. *Natural fit: the object carries its own small light sources or one flammable/luminous component, or is very small in frame:* model ships, lanterns, vehicles with lights, lit windows, tiny relics under 25% width, anything where spikes would overpower the shape.
- **Rim-glow-led:** cool cyan-lavender edge light traces the silhouette while the interior stays dark; used with a small warm hot spot on top. *Natural fit: the object is a large matte form whose outline matters more than its surface:* stone, marble, plaster, wood, leather, architecture, sculpture, silhouettes.
- **Single-flare-led:** one hot white-blue flare at exactly one joint, notch, or edge; the rest of the object stays a dark near-silhouette with only a faint pink-violet sheen on its texture. *Choose when the value relationship is dark-relic-on-light-field, or when the object is dark rough metal, iron, or weathered wood whose identity is its outline plus one point of power* (war hammer, axe, anchor, bell).

When several fit, the material covering more of the silhouette usually leads.

Figure light treatment · 人物光则 (applies whenever the subject is a human figure, in any grammar):

- **Body-color aura:** the figure emits a soft glow in its own dominant clothing or body hue — a red suit bleeds red-pink, a blue robe bleeds blue — extending 2–6% of frame width beyond the silhouette, brightest at head and shoulders.
- **Restrained glitter shell:** a sparse scatter of fine soft-glowing particles (roughly 30–120, denser behind than in front) floats in the aura zone around the figure. Restrained means countable, not a coating; the shell is part of figure treatment and stacks freely with any particle voices.
- **Spikes belong to objects; bloom belongs to people.** Star-filter diffraction spikes never appear on a human body, face, or eyes. Human highlights — eyes, skin, sweat, cloth — render as soft CCD-style sensor bloom: a small clipped core (≤0.5% of frame width) inside a wide soft halo with a faint magenta fringe, like an early digital camera blooming on a highlight. Hard sparks stay on the equipment and surroundings (ring ropes, car body, helmet rim).

Particle vocabulary — the style's signature atmosphere. These combine freely and carry **no fixed pairings**: the scenes in parentheses are where each first appeared, not where it belongs:

- **Sparkle drift:** a thin trail of glitter dust leaving one edge of the object, direction consistent with its attitude (hammer trailing dust, gold spray off a sail); the trail stays narrow — 2–6% of frame width — never a broad diagonal band.
- **Dust cloud:** one small detached cluster of 20–60 cool blue micro-sparkles floating inside or beside the relic (the galaxy inside a wreath), confined to one region no larger than 15% of the frame; a single point of light is not a cloud.
- **Hover fringe:** blue-white glitter gathered along the object's bottom edge only, 1–3% of frame height thick, as if levitation itself sheds light (architecture).
- **Sparkle fountain:** a dense spray of particles rising and falling behind a figure (first seen behind a figure on their machine; any subject may erupt).

Dosage over selection: one particle voice dominant, the others quiet; particles gather in meaningful regions — around the subject, along an edge, inside a hollow — and thin out fast. Never a uniform frame-wide coating. In the compiled prompt, the companion gets its own sentence with a count and a region bound — companions described loosely get dropped or diluted by the generator.

Color rules:

- The field is always cool (cobalt / ultramarine / mid royal blue / near-black).
- The relic's highlights are always warm: gold, copper, bronze, pink-red, cream, or a pink-violet sheen on dark metal. One warm hue family per image; a red object (hoop rim, crest, racing suit) counts as that hue.
- White-hot only at spike and flare centers.
- In the dark-relic relationship, the object may be near-black; its single flare is white-blue with a warm fringe.
- No green, no yellow field light, no rainbow, no second cool hue besides the split's cyan.

Structural test: cover the spikes and glitter with your thumb. If the image is still just a product photo on blue, the light is decoration — redistribute it so it changes the object's outline, weight, or direction.

## Film Reproduction · 胶片再现

- Look: 35mm color negative shot at high ISO on a dark set — slight softness, gentle halation, grain in every value.
- Chromatic aberration is allowed on high-contrast edges and mandatory on spikes. On human subjects, highlights bloom like an early-2000s CCD sensor — clipped core, wide soft halo, faint magenta fringe — never spiking.
- Highlights may clip to white; the object may lose detail in shadow. Do not recover shadows.
- No sharpening halos, no HDR, no denoising smoothness, no digital lens-flare overlays, no glossy render reflections.

## Micro-Text · 文字

None by default. If the user asks for text, keep it to one small line (English ≤5 words or Chinese ≤8 characters) in a quiet lower or upper region, in a plain sans or typewriter face, off-white at 60–80% opacity, never touching the object or the spikes.

## Prompt Shape · 提示词骨架

Write the final prompt as four compact paragraphs, in this order:

1. **Canvas and field:** ratio, field variant with end colors, value relationship, grain, dust specks, emptiness (explicitly: no ground, no horizon, no shadow, no other objects, no text).
2. **Relic and attitude:** the object, its material, what stays recognizable, subject grammar, size share, position, tilt, what was removed.
3. **Light grammar:** primary + supporting grammar, spike point count and counts, spike length, chroma split, glitter density, halation, particle companion (if any) with its region, warm highlight hue, shadow share.
4. **Film reproduction and hard avoids:** film stock feeling, aberration, clipping, and the avoid list.

Compile only instructions that become pixels. Name what must disappear as clearly as what must appear. State once, plainly: `Only one object exists in the frame.`

## Workflow · 流程

1. Build the Relic Card; write the discard list.
2. Choose canvas, background variant, subject grammar, attitude.
3. Fix size share, position, and tilt numbers.
4. Choose one primary light grammar (+ optional supporting); set spike point count and counts; set warm hue.
5. Run the structural test on the light plan.
6. Compile the four-paragraph prompt.
7. Generate. Inspect at full size and thumbnail.
8. Regenerate at most once with a targeted correction.
9. Return the image and a 1–3 sentence Chinese note.

## Targeted Correction · 定向修正

Regenerate once, fixing only the observed failure:

- **Ground or horizon appeared:** restate the empty gradient; remove floor, table, sky line, reflection.
- **Object too big / too low:** restate the 30–50% width and 42–52% height-center ranges.
- **Object fully lit / flat:** demand 50–70% shadow, one hard key, small hot points.
- **Spikes look like neon rays or stickers:** thin them, soften them, restore magenta–cyan split, cut count by half.
- **Rainbow / green / yellow field:** restate cool cobalt field, one warm hue on the relic.
- **Too clean / digital:** add grain in shadows, halation, slight softness; remove HDR and sharpening.
- **Extra objects, hands, stand, text:** restate `Only one object exists in the frame.`
- **Particles coat the frame uniformly:** restate dosage — one dominant voice, meaningful regions, fast falloff.
- **Eyes, skin, or clothing render as starbursts:** replace with soft CCD bloom — small clipped core, wide halo; spikes stay on objects.
- **Figure missing the treatment (no aura, no particles, plain photo look):** restate body-color aura, particle shell, and mostly-dark exposure.
- **Dark relic lost against a dark field:** switch to the day-for-night field variant, state "mid royal blue all the way to the top", and restate the single flare.
- **Companion dropped or shrunk to a dot:** give the companion its own sentence with a count (e.g. 20–60 micro-sparkles) and a region bound.
- **Drift became a broad light band:** restate a thin trail, 2–6% of frame width, off one edge only.
- **Object planted at or cropped by an edge:** restate full containment, ≥8% margin, floating with 8–20° tilt.
- **Silhouette shows a face:** flatten to pure dark shape, backlight only.
- **Debris scattered everywhere:** confine fragments below the object; keep 60%+ intact.

## Hard Avoids

Ground planes, floors, tables, horizons (exception: the black foreground band of figure scenes), skies with clouds, starfields, galaxies, nebulae, auroras, light rays or god rays, anamorphic horizontal streaks, digital lens-flare overlays, bokeh circles, neon outlines, glow tubes, rainbow or multi-hue flares, green or yellow field light, gradients with visible banding, vignette rings, cast shadows, mirror reflections, motion blur, smoke, confetti, multiple unrelated objects, hands or stands, packaging, product-shot studio sweep, HDR, over-sharpening, denoised smoothness, 3D-render plastic sheen, glossy CGI metal, cartoon or vector styling, star-filter spikes on any human body, face, or eyes, watermarks, logos, and any text not explicitly requested.

## Output Format

```markdown
![Starlit Relic](image)

**创作说明**

[1–3 句中文：这件物体是什么、以什么姿态悬置、光如何落在它身上。]
```

Add the prompt or a parameter list only when the user explicitly requests it.

## Quality Gate

Before returning, confirm all ten:

1. Only one object (or one inseparable group — a figure with its relic counts as one) exists in the frame.
2. The field is one empty cool-blue variant with grain and no horizon (figure scenes may keep their black band).
3. The relic is recognizable at thumbnail size.
4. Subject sits at 40–55% height, 25–50% width (grammar caps aside), optically centered.
5. 50–70% of the object is in shadow (near-total for dark-relic frames); highlights are small and warm.
6. Spikes are thin, single point-count, chroma-split, and appear only on objects — human figures carry aura, shell, and CCD bloom instead.
7. The field is cool; the relic carries exactly one warm hue family.
8. Grain, halation, and aberration read as film, not as effects.
9. The object floats fully inside the frame (≥6% margin to every edge) with no support, shadow, or reflection.
10. No text, logo, or watermark unless requested.
