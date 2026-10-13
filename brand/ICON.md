# Most Likely To icons

The mark is a pointing finger above three round friend faces: one person
points at who is most likely to. Flat, no text, two colours per version.

## Files

| File | Use | Pairing |
| --- | --- | --- |
| `icon.png` / `icon.svg` | App icon, set as `icon.image` in `dapp.json` (emoji 🎭 stays the fallback). 1024×1024. | Black `#000000` tile, Yellow `#FFEE6F` mark |
| `featured-light.png` / `featured-light.svg` | Featured illustration for the Homeroom directory, light. 1600×900. | Cream `#FFFEEA` ground, Black `#000000` mark |
| `featured-dark.png` / `featured-dark.svg` | Featured illustration for the Homeroom directory, dark. 1600×900. | Black `#000000` ground, Yellow `#FFEE6F` mark |

Colours come from the Homeroom brand palette: Cream `#FFFEEA`, Yellow
`#FFEE6F`, Black `#000000`. The featured files exist as files only: the
platform has no manifest field for a featured illustration yet, so the
directory picks them up once it reads from here. The app icon is wired in
`dapp.json`; the platform rounds and crops the tile, and the mark sits well
inside the square so the crop never cuts it.

## Geometry

One 1024 grid is shared by every file; the featured versions draw the same
mark scaled 0.7 and centred.

| Part | Geometry |
| --- | --- |
| Sleeve | rect x 420, y 96, 184×64, rx 16 (16 px ground gap above the fist) |
| Fist | rect x 380, y 176, 264×190, rx 72 |
| Index finger, pointing down | rect x 468, y 300, 88×230, rx 44 (tip at y 530) |
| Side faces | circles at (282, 786) and (742, 786), r 100 |
| Middle face (the one pointed at) | circle (512, 742), r 128, drawn last with a 28 px ground-colour stroke so it separates from the side faces |
| Eyes | ground-colour dots: r 14 at (472, 725) and (552, 725); r 12 at (252, 770), (312, 770), (712, 770), (772, 770) |
| Smile | path `M466 790 Q512 830 558 790`, ground-colour 14 px round stroke |

Everything sits inside x 182 to 842 and y 96 to 886. The browser tab
favicon reuses the same shapes inline in `public/index.html` (without the
sleeve, eyes and smile, which vanish at 16 px), on a rounded square with
rx 224, because browsers do not round the tab icon themselves.