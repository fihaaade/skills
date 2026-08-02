---
name: phosphor-relay-style
description: Create Phosphor Relay images — photographs of a live broadcast re-shot off a glowing screen, where the display's phosphor grid is the dominant material. Use when the user asks for CRT/screen re-photography, broadcast stills, lo-fi sports or televised imagery, signal-decay aesthetics, or scanline-grid photographic treatments.
---

# Phosphor Relay

Photograph a screen, not a scene. Every image is one camera pointed at one glowing display carrying broadcast footage, at a distance close enough that the display's phosphor grid becomes the picture's material. Generate the image by default when image generation and image inspection are both available; otherwise return the compiled prompt and recipe.

## Visual identity

Build every image from these invariants:

- **Second-hand light:** the only light source in the frame is the display itself. Nothing is lit by the sun, a lamp, or a flash. The image is a record of an emission, not of an object.
- **Grid as material:** the phosphor grid — RGB stripe, aperture grille, or shadow-mask dot triad — is continuously visible across the entire frame. It is the picture's skin, not an overlay, and it survives in highlights, shadows, and blur alike.
- **Fine weave, not coarse dots:** the grid is dense and fine — on the order of 300-600 stripes or dot columns across the frame width, never tens. At full size it reads as woven cloth or fabric mesh laid over the image. A grid coarse enough to count by eye is wrong.
- **Moiré is mandatory:** the grid interferes with both the sensor and the depicted content, producing a visible beat — wavy interference bands, dot size that swells and shrinks across the frame, a slight off-axis rotation, and occasional aliasing where fine content meets fine grid. A mechanically regular, perfectly even lattice is a halftone filter, not a photographed screen, and is a failure.
- **Cold field, one warm event:** cyan-teal governs 60%-85% of the color field. Red, magenta, or orange appears as **one contiguous warm mass** occupying roughly 3%-15%. The warm mass is always **a thing in the scene** — a shirt, a hoarding, a stand, a running track — with the scene's own softness, grid, and luminance failure applied to it. A flat saturated rectangle sitting on top of the image is a designed swatch, not a photographed object, and is a failure.
- **Two-ended luminance failure inside a midtone frame:** highlights bloom and fuse (white kit melts into a single mass, edges gone); shadows crush to dead black with zero recoverable detail (a face under a hood is a solid void). Both failures are present, but together they occupy no more than about 35% of the frame. The remaining midtones carry all the information. A frame that is only blown white and dead black has no picture in it.
- **Nothing is sharp except the grid:** the depicted subject is soft, defocused, motion-smeared, or interpolated. Optical sharpness belongs only to the phosphor structure. Subject edges dissolve into the grid rather than cutting across it — a clean, hard-edged silhouette inverts the rule and is a failure. Resolve this contradiction in every frame.
- **The uneventful moment:** depict what happens **around** the decisive action — walking, waiting, a back turned, the seconds after a celebration, an empty stand, a shoe, a hand. Never the goal, never the strike, never the peak.
- **In-scene text, never overlay text:** text that physically exists in the photographed scene belongs here — a name or number on a shirt, sponsor lettering on a hoarding, script on a boot, a sign, a destination board. It arrives degraded: broken by the grid, partly swallowed by bloom, legible in fragments, never crisp. What is forbidden is the compositing layer — scoreboard bugs, clocks, network logos, subtitles, lower-thirds, watermarks, captions — because those were never in front of the camera.
- **No frame furniture:** no borders, mockups, screen bezels, or room context. The display fills the picture edge to edge.
- **Anonymous bodies:** subjects are read as figures, not as identified people. Faces are cropped, turned away, blurred, blacked out, or too degraded to identify.

Use the reference set to anchor grid density, color governance, luminance failure, and crop courage.

## Two modes

**Treat** is the primary mode. Phosphor Relay is a material system, and any photograph can be put through it.

- **Treat** — the user supplies a photograph. Keep its subject, composition, crop, and moment; force the full material system onto it. The register, scale, and moment are read off the photo, not chosen. Only signal state, chroma event, focus behavior, and grid behavior remain free choices.
- **Originate** — no photograph supplied. Choose every axis from the variation engine and build the frame from a brief.

When a photo is supplied, default to Treat. Switch to Originate only if the user asks for a new frame merely inspired by it.

### What Treat inherits and what it overrides

This split is the whole mode. Getting it wrong produces a photo with a grid laid on it, which is the characteristic Treat failure.

**Inherited from the photo, never changed:** subject, composition, crop, framing, moment, and any text present in the scene. Do not recompose, do not add or remove subjects, do not clean up, do not restage.

**Overridden onto the photo, always, regardless of what the photo looks like:** the grid, the cold field, the single warm mass, the two-ended luminance failure, and the soft-subject-sharp-grid inversion. These are not inherited. A warm, evenly-exposed, sharply-focused source photograph must come out cold, blown-and-crushed, and soft. If the output's color temperature and tonal distribution are not obviously different from the source, the treatment did not happen.

Two cases the mode must handle explicitly:

- **The photo has no warm element.** Run `cyan-only`. Do not invent a warm mass.
- **The photo is warm-dominant, or its warm areas exceed the 3%-15% share.** Keep the single strongest warm object as the warm mass and desaturate every other warm region into the cold field. A warm subject filling the frame is desaturated to cold with one region held back as the event. Never let the source's warmth govern the output.

## Formats

- Use `4:3` by default. This is the native register of the source material and the correct answer unless told otherwise.
- Use `3:2` only when the user asks for a wider frame.
- Use `1:1` only when the user asks for a square.
- Honor exact dimensions supplied by the user.

## Capture registers

Choose one primary register. Add at most one subordinate register when the frame genuinely holds two.

| Register | Best for | Typical scale | Grid behavior |
| --- | --- | --- | --- |
| Close signal | faces, napes, hands, boots, fabric, single objects | subject fills 60%-100% of frame | grid coarsest and most legible; reads as woven cloth |
| Field action | duels, runs, contested space, two-to-five figures | figures 25%-60% of height | grid competes with motion; partial smear |
| Held still | a back turned, waiting, walking out, standing alone | figure 20%-50% of height, large empty pitch | grid quietest; emptiness carries the frame |
| Crowd and structure | stands, terraces, stadium bowls, aerial geometry | no single subject; texture is subject | grid interferes with crowd pattern into moiré |
| Dissolved | multi-frame ghosting, horizontal tearing, unrecognizable color mass | subject unreadable by design | grid is the only stable element left |

## Variation engine

Before compiling, choose exactly one option per axis. Randomness must change **what kind of picture this is**, not merely where the subject sits. If recent outputs shared a register or signal state, choose differently.

### Frame structure

- **single:** one full-bleed frame
- **diptych-even:** two frames butted at a hard vertical seam near center, no gap, no rule
- **diptych-offset:** hard vertical seam at roughly 1:2 or 2:1, the narrower panel carrying the stranger image
- **stacked:** one hard horizontal seam, upper and lower registers from different moments

Diptych panels must differ in register or signal state. Two similar panels are a failure.

### Signal state

- **stable:** clean grid, coherent geometry, only softness and bloom
- **ghost:** interlaced multi-exposure trailing — one figure resolving into 3-5 offset copies
- **smear:** horizontal directional pull, subject stretched along the scan direction
- **tear:** displaced horizontal bands, misregistered blocks, a broken line across the frame
- **dissolve:** subject collapsed into unreadable chromatic mass; only grid and color remain

### Chroma event

- **cyan-only:** no warm mass; teal and steel govern everything, tension comes from luminance alone
- **cyan-plus-red:** one contiguous red or magenta mass against the cold field
- **pitch-green:** desaturated turf green governs the lower field, cyan the upper
- **bloomed:** highlights so blown the frame reads near-white with cyan only in shadow
- **crushed:** shadow so dominant the frame reads near-black with cyan only in highlight

### Focus behavior

- **grid-sharp:** phosphor structure resolved, subject soft
- **double-soft:** both slightly off, moiré beating against subject edges
- **collapsed:** heavily defocused, grid persisting as the only edge in the frame

### Moment

- walking out
- waiting between phases
- the seconds after
- a back turned
- an object at rest
- an empty section of stand
- crowd as weather
- the pitch from above

## Workflow

### 1. Lock the brief

Identify the subject matter, emotional temperature, output format, register, frame structure, and execution mode. Infer only what the user left open, using the defaults above.

Set execution mode to `rendered` only when image generation and image inspection are both available. Use `prompt-only` when the user asks for it or either capability is unavailable.

If the user names a specific real, identifiable person, do not render a likeness. Convert the request into an anonymous figure in the same context — cropped, turned, or degraded past identification — and say so in one line at delivery.

Completion criterion: all six values are explicit, and any unavailable capability is recorded.

### 2. Distill the frame

Write one internal sentence naming what is on the screen and what the camera is doing to it. Prefer a situation over an action, and a fragment over a whole.

Completion criterion: the frame is describable in one sentence, and that sentence contains no decisive action.

### 3. Lock quality anchors

Read [references/example-index.md](references/example-index.md) and select one or two entries matching the chosen register. Inspect each linked image when image inspection is available; otherwise use the entry description. For every selected anchor, record one anchor delta:

- three invariants to preserve;
- three axes to change across frame structure, signal state, chroma event, scale, focus, moment, or subject matter.

Use the examples as quality anchors, not compositions. Never pass sample filenames, source provenance, team names, kit details, or sample-specific content into the image prompt.

Completion criterion: every selected anchor has a three-invariant, three-axis delta, and the planned frame satisfies each delta.

### 4. Declare the recipe

Choose exactly one value for each axis:

- format: `4:3`, `3:2`, `1:1`, or supplied dimensions;
- register: close / field / held / crowd / dissolved;
- frame: single / diptych-even / diptych-offset / stacked;
- signal: stable / ghost / smear / tear / dissolve;
- chroma: cyan-only / cyan-plus-red / pitch-green / bloomed / crushed;
- focus: grid-sharp / double-soft / collapsed;
- moment: one entry from the moment axis;
- grid: stripe / aperture-grille / shadow-mask-dot, plus the moiré behavior (wavy banding, swelling dot size, off-axis rotation, or aliasing against fine content). Density is not a choice — it is always fine, 300-600 across the frame width;
- text: none, or the in-scene text that is present and how far it degrades;
- subject: one short phrase naming what is on the screen.

In Treat mode, `register`, `frame`, and `moment` are transcribed from the supplied photo rather than chosen, and `mode: treat` is recorded alongside them.

Completion criterion: all nine axes carry one declared value and support the same frame.

### 5. Compile the image prompt

Write four compact paragraphs containing only information that should become pixels:

1. **Apparatus and frame.** State that this is a photograph of a glowing display filling the frame edge to edge, the ratio, the frame structure and seam position, and that the display is the only light source.
2. **What is on the screen.** State the subject, register, scale within frame, crop boundaries, and the moment. Say explicitly what is cut off by the frame edge.
3. **Signal and material.** State the grid type, that it is fine and dense, and its named moiré behavior. Then state the signal state, the focus behavior with subject edges dissolving into the grid, the chroma event naming the warm mass as an object in the scene with its approximate share and single location, and the two-ended luminance failure inside a midtone-dominant frame.
4. **Finish and rejections.** State the flat second-hand-light finish and the rejection constraints below.

Paragraph 3 must carry all three of the following in some form. These are the fields the model silently drops, and each one is a gate:

- `the stripe pattern remains legible inside the blown white areas and inside the crushed black areas`
- `the grid is fine and dense, hundreds of stripes across the frame width, with visible moiré beating and uneven dot size, not a regular halftone lattice`
- `most of the frame sits in midtones; blown and crushed areas together stay under roughly a third`
- `only the phosphor structure is sharply resolved; the depicted subject is soft throughout`

That last sentence does double duty: binding sharpness explicitly to the grid is what makes the model render a fine dense weave instead of coarse dots. Never let `sharp` float free in the prompt.

Be decisive about position, crop, moiré behavior, warm-mass location, and where luminance fails. Keep analysis notes, recipes, filenames, and provenance outside the prompt.

Completion criterion: the prompt answers all four fields, paragraph 3 carries all three mandatory sentences, and the frame contains no decisive action.

When execution mode is `prompt-only`, stop here. Return the exact compiled prompt and the complete recipe from Step 4 with status `PROMPT_ONLY`; skip generation and QA. Add one concise capability note outside the prompt only when the mode is a fallback.

### 6. Generate one candidate

Use the built-in image generation capability at the selected ratio.

In **Treat** mode, edit the supplied photograph rather than generating a new scene. The output must be recognizably the same picture — same subject, same framing, same moment — put through the material system. If the result reads as a different photograph, the treatment failed and the edit was too strong.

In **Originate** mode, generate from the compiled prompt.

Completion criterion: one inspectable candidate exists at the requested ratio.

### 7. Inspect and repair

View the candidate at full size and at thumbnail size before presenting it. Check every critical gate. Treat the first render as a candidate, not a final.

Zoom to at least three separate areas — one highlight, one shadow, one midtone — and confirm the grid is present in all three. Grid that survives only in midtones is a failure.

If any gate fails, read [references/repair-playbook.md](references/repair-playbook.md), identify the single largest defect, tighten only the relevant prompt fields, and regenerate once.

Completion criterion: every critical gate passes. If the repaired candidate still misses a gate, label the result `DONE_WITH_CONCERNS` and name the remaining defect.

### 8. Deliver

Show the accepted image first, then the exact final prompt and the complete recipe plus status. Include a saved path only when the image was saved into the user's workspace. Return no attribution or provenance note.

## Critical gates

Require all of the following:

- Correct requested ratio, with a crop designed for that ratio.
- The phosphor grid is unmistakably visible across the whole frame, including inside highlights and shadows, and reads as physical screen structure rather than added noise.
- **The grid is legible inside every crushed black region.** Zoom into each black area and confirm. A black shape with no grid in it is the single most common failure in this style.
- **The grid is fine and dense**, hundreds of stripes or dot columns across the frame width. If the dots can be counted by eye, it is too coarse.
- **The grid shows moiré** — wavy beat bands, uneven dot size, or off-axis rotation. A mechanically perfect lattice fails.
- The image reads as a photograph **of a CRT or LCD carrying broadcast footage**, not as a digitally filtered photograph, not as generated glitch artwork, and not as a stadium LED billboard.
- Cyan-teal governs the field; any warm mass is single, contiguous, within share, and reads as an object in the scene rather than a flat swatch laid on top.
- Highlights bloom and fuse; shadows crush to black. Both failures are present, and together they stay under roughly a third of the frame, leaving midtones dominant.
- The subject is soft while the grid is sharp. Subject edges dissolve into the grid; no clean hard-edged silhouette.
- The depicted moment is not a decisive action.
- Any text present is in-scene and degraded — broken by the grid, partly swallowed by bloom, legible only in fragments. No crisp, fully readable lettering.
- No overlay layer: no scoreboards, clocks, network logos, subtitles, lower-thirds, watermarks, or captions. No borders, bezels, or room context.
- No identifiable real individual.
- Diptych panels, when used, differ in register or signal state and meet at a hard seam.
- The image reads at thumbnail size as a cold, degraded, quiet frame, and rewards full-size inspection with grid structure.
- Every recorded anchor delta passes.
- In Treat mode: the composition is recognizably the source photograph, **and** the color temperature and tonal distribution are obviously different from it. A source photo that comes out merely gridded — still warm, still evenly exposed, still sharp — is the characteristic Treat failure and does not pass.

Reject candidates that resolve into: a clean sports photograph, a film-grain analog look, retro VHS pastiche, vaporwave or synthwave, neon cyberpunk, generated glitch art, a datamosh effect, a Photoshop halftone or color-halftone filter, a regular print dot screen, a stadium LED billboard or scoreboard panel, pixel art, a color-bar test pattern, a flat saturated color swatch, a screen inside a room, a device mockup, a poster with typography, or a recognizable copy of a reference frame.

## Banned wording

These words pull the model away from the identity and must not appear in the compiled prompt unless the user explicitly asks for that quality:

- `film grain`, `35mm`, `analog film`, `kodak`, `portra`, `cinestill`, `darkroom` — this is an emitted screen, not exposed film. Naming film destroys the grid.
- `subtle texture`, `light grain`, `slight noise`, `gentle overlay`, `scanline overlay` — the grid is structural and dominant, never subtle and never an overlay.
- `halftone`, `dot screen`, `evenly spaced dots`, `regular dot pattern`, `uniform grid`, `crisp dot matrix`, `pixel art`, `LED panel`, `LED billboard`, `dot matrix display` — these all produce a mechanically perfect lattice. The grid must beat, drift, and vary. Say `moiré`, `interference`, `beat pattern`, `uneven`, `off-axis` instead.
- `silhouette`, `crisp outline`, `clean edges`, `hard-edged shape`, `cutout`, `vector shape` — subject edges dissolve into the grid. A shape that cuts cleanly across the grid inverts the identity.
- `glitch art`, `datamosh`, `vaporwave`, `synthwave`, `neon`, `cyberpunk` — degradation here is physical and accidental, not stylized or designed.
- `sharp`, `crisp`, `high resolution`, `4K`, `HDR`, `detailed`, `ultra detailed` — the subject is low-fidelity by definition. Apply `sharp` only to the grid.
- `warm`, `golden hour`, `sepia`, `nostalgic warm tones`, `vintage warmth` — the field is cold. Warmth exists only as the single contiguous mass.
- `dramatic`, `epic`, `dynamic`, `action shot`, `decisive moment`, `peak action` — the moment is uneventful.
- `vibrant`, `saturated colors`, `colorful` applied to the frame as a whole — only the warm mass and the cyan field carry color; everything else is degraded.

Apply `soft`, `blurred`, and `low contrast` to the depicted subject only. Never describe the grid as soft, and never describe the whole image as low contrast — the luminance failure at both ends is high contrast.

## Output shape

For `PROMPT_ONLY`, omit the Image section.

````markdown
**Image**

![Phosphor Relay frame](absolute-image-path-or-rendered-image)

**Final prompt**

```text
[exact prompt used for the accepted image]
```

**Recipe**

- Mode: [treat/originate]
- Format: [ratio]
- Register: [register]
- Frame: [structure]
- Signal: [state]
- Chroma: [event]
- Focus: [behavior]
- Moment: [moment]
- Grid: [type + moiré behavior]
- Text: [none / in-scene text and its degradation]
- Subject: [short phrase]
- Status: [DONE/DONE_WITH_CONCERNS/PROMPT_ONLY]
````
