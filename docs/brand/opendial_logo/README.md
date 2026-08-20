# OpenDial logo

The mark is a headset octopus: the arms stand for conversations handled in
parallel, which is what the product does. As channels are added at Milestone 11
the metaphor widens with the product rather than fighting it.

Open `index.html` in a browser for the same information laid out visually, with a
switcher for treatment and colour, dark and light backgrounds, and a size ladder.

## Treatments

| Treatment | What it is | When to use it |
|---|---|---|
| Full colour | The original artwork, gradients and all | Anywhere above ~64 px: site, README, slides |
| Knockout | Solid body, headset and face punched out. One flat colour | The single-colour mark to reach for first. Favicon, app chrome, print |
| Outline | Linework only. One flat colour | Light use above ~64 px. The tentacles fragment below that |
| Silhouette | Outer shape only, no interior detail | Masks, cut vinyl, anywhere only a shape is wanted |

## Colours

Full colour comes in purple and white. Every single-colour treatment comes in
purple, white and black. **There is no black full-colour version** — black is a
single-colour treatment only.

| Role | Purple mark | White mark |
|---|---|---|
| Body | `#9F50F8` | `#E7E7FB` |
| Body shadow | `#5425DA` | `#5B57FA` |
| Headset | `#291A6E` | `#1F1A76` |
| Outline | `#120A50` | `#07072A` |

Flat purple is `#9F50F8`.

## Files

Everything sits flat in this folder.

| File | Use |
|---|---|
| `index.html` | Visual sheet. Self-contained — every mark is embedded, so it renders even if moved |
| `opendial-octopus-{purple,white}.svg` | Full colour. Purple works on dark and light; white needs a dark background |
| `opendial-octopus-{purple,white}-{512,256,128,64,32}.png` | Full colour, transparent raster |
| `opendial-octopus-flat-{purple,white,black}.svg` | Knockout, one flat colour |
| `opendial-octopus-line-{purple,white,black}.svg` | Outline, one flat colour |
| `opendial-octopus-solid-{purple,white,black}.svg` | Silhouette, one flat colour |
| `opendial-octopus-flat-{purple,white,black}-{64,32,16}.png` | Knockout at icon sizes. Favicon and app chrome |
| `original-artwork.png` | The raster original everything here was traced from |
| `original-variant-sheet.png` | The four-variant sheet the artwork came from |

## Known limits — read before using these as masters

**Everything here is traced, not drawn.** All of it was vectorised from
`original-artwork.png`. The files render faithfully and scale cleanly, but the
full-colour marks are roughly 200 colour-band paths each, so a colour cannot be
changed by editing one value and a shape cannot be moved without breaking the
shading. They are also heavy for a logo, around 230–280 KB each.

**Full colour does not survive small sizes.** Below roughly 48 px the face and the
headset collapse into a blob. Use the knockout treatment instead — it stays
readable to about 32 px.

**Nothing here is legible at 16 px.** Every treatment is a smudge at that size. A
purpose-drawn 16 px icon is still missing.

Redrawing the mark as clean editable vector, plus a purpose-drawn icon, is parked
in `IDEAS.md`. It is not Milestone 0 work.
