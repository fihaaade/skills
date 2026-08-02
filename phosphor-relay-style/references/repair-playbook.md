# Repair playbook

Read this only after a candidate fails a critical gate. Choose the single largest defect and apply the matching correction. Preserve the rest of the prompt. Regenerate once.

| Failure signal | Prompt correction |
| --- | --- |
| Grid is faint, decorative, or reads as an overlay | Name the grid type explicitly (`vertical RGB phosphor stripe`, `aperture grille`, `shadow-mask dot triad`), raise stated coverage to 40%-60%, and state that the grid remains visible inside blown highlights and crushed shadows. Remove any word suggesting subtlety. |
| Grid survives only in midtones | State that the grid persists at both luminance extremes: `the stripe pattern remains legible inside the blown white mass and inside the black void`. Name the specific black region: `the figure's dark mass is filled with visible stripe structure, not solid black`. |
| Grid is a mechanically perfect lattice, reads as a halftone filter | Remove every word implying regularity. State `visible moiré beating between the camera sensor and the screen grid, dot size swelling and shrinking across the frame, the grid rotated slightly off-axis, aliasing where fine content meets fine grid`. |
| Grid is too coarse, dots countable by eye | State `fine dense grid, hundreds of stripes across the frame width, reading as woven fabric mesh at full size`. Remove `dot`, `dot matrix`, and any word suggesting discrete large cells. |
| Image reads as a stadium LED billboard or scoreboard | Restore midtones: state `most of the frame sits in midtones, the grid carries continuous tone rather than discrete lit cells on black`. Remove pure-black-background language and any `LED` reference. |
| Frame is only blown white and dead black, no picture in it | State `blown and crushed areas together stay under roughly a third of the frame; the remaining midtones carry the subject`. |
| Subject is a clean hard-edged silhouette | State `the subject's edges dissolve into the grid, soft and interpolated, never cutting cleanly across the stripe pattern`. Remove `silhouette`, `outline`, and `cutout`. |
| Warm mass is a flat saturated rectangle | Name it as an object in the scene and apply the scene's treatment to it: `a red hoarding along the lower third, carrying the same grid, softness, and bloom as the rest of the frame`. Remove any wording that reads as a color block or swatch. |
| Image looks like film, not a screen | Remove every film reference. State `photograph of a glowing display, the screen is the only light source, no ambient light falls on the subject`. Add `emitted light, not reflected light`. |
| Image looks like stylized glitch art | Replace designed-corruption language with apparatus language: interlace trailing, tracking error, misregistered scan bands, moiré between camera sensor and screen. State `accidental transmission failure, not designed effect`. |
| Subject is too sharp | State `the subject is defocused and low-fidelity; only the phosphor structure is resolved`. Add the contradiction explicitly: `sharp grid over soft subject`. |
| Color is warm, neutral, or evenly distributed | Restate cyan-teal governance at 60%-85%, and place the warm mass at one named location covering a stated share. Remove all warm-tone atmosphere language. |
| Warm accents are scattered | Collapse them into one contiguous object or plane and name it: `a single red hoarding along the lower third` or `one magenta shirt at the right edge`. |
| Highlights and shadows both hold detail | State both failures: `white areas bloom and fuse into a single edgeless mass; shadow areas crush to pure black with no recoverable detail`. |
| An overlay layer appears — scoreboard, clock, logo, subtitle, watermark | State `no compositing layer of any kind: no scoreboard, no clock, no network logo, no subtitle, no lower-third, no watermark, no caption`. In-scene text stays. |
| In-scene text is crisp and fully readable | State `the lettering is broken by the stripe pattern, partly swallowed by bloom, and legible only in fragments`. Never let text render cleanly. |
| Treat mode returned a different photograph | The edit was too strong. State `preserve the source subject, framing, crop, and moment exactly; change only material, color, luminance, and grid`. Reduce every generative instruction. |
| Treat mode barely changed the photo | The edit was too weak. Raise grid presence and both luminance failures first; those two carry the identity. Leave composition alone. |
| Treat mode applied the grid but kept the photo's own color and exposure | The most common Treat failure. State that the cold field, the single warm mass, and the two-ended luminance failure are forced onto the image regardless of the source: `push the whole frame to cold cyan-teal, blow the brightest areas until they fuse, crush the darkest to black, keep only one warm region`. |
| Treat source is warm-dominant and the output stayed warm | State `desaturate every warm region into the cold field except one, which stays as the single warm mass`. Name which region is held back. |
| Treat output subject is still sharp | State `the subject goes soft throughout; only the phosphor structure is resolved`. Source sharpness is never inherited. |
| A screen bezel, device, or room appears | State `the display fills the entire frame edge to edge; no bezel, no device body, no wall, no room, no reflection`. |
| The moment reads as peak action | Replace the moment with an entry from the moment axis and state what is *not* happening: `no ball in play, no contact, no celebration at peak`. |
| Diptych panels look alike | Assign the two panels different registers and different signal states, and state the seam ratio numerically. |
| Diptych seam is soft or decorated | State `hard vertical butt seam, no gap, no border, no rule, no blend, panels touch directly`. |
| Frame reads as a clean sports photograph | Lower fidelity across the board: add interlace trailing or directional smear, raise grid coarseness, deepen the luminance failure at both ends. |
| Face is identifiable | Crop past the face, turn the figure away, or crush the face to a black void. State `face not visible`. |
| Candidate resembles a quality anchor | Rebuild the anchor delta with three stronger axis changes, then regenerate. |
