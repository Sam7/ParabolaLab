# PARABOLA LAB

A self-contained, offline-capable web application for designing a 3D-printable paraboloid reflector.

## Run

Open `index.html` in a modern browser (Chrome, Edge, Firefox or Safari). No installation, server, npm, external fonts, libraries or API keys are needed. WebGL is used for the 3D preview; printable geometry is generated in the browser.

To publish it as a website, upload `index.html` to the root of a GitHub Pages site, or deploy the directory to any static web host.

## Parameters

* **Aperture diameter (D)**: Inner opening diameter in mm.
* **Dish depth (h)**: Height from inner vertex to inner rim in mm.
* **Wall thickness (t)**: Offset normal to the inner parabolic profile in mm.
* **Flat base diameter**: Diameter of a flat contact pad beneath the reflector, in mm; 0 disables it.
* **Focal length (f)**: Distance along the centre axis from the inner vertex to the focus. Editing the focal length changes depth automatically.
* **Resolution**: Number of facets around the reflector (48–256). Radial segments adapt to this resolution.

The ideal reflective surface follows **z = r² / (4f)** and **f = D² / (16h)**. All quantities are measured in millimetres.

## Export and slicing

Click **Download printable STL**. The app constructs a solid, closed triangle mesh comprising the inner surface, surface-normal-offset outer surface, rim, and optional flat base. The STL is binary. Its lowest point is shifted to Z=0; it is intended to be imported as millimetres (STL format itself has no embedded units).

The default model is D=220 mm, h=45 mm, t=3 mm, flat base=36 mm, f≈67.22 mm. Its actual external diameter is approximately 223.80 mm and its mesh volume is 134.20 cm³ (about 166.4 g of PLA before supports, infill choices and any slicer modifiers).

**Important:** A flat contact pad does not imply the entire curved underside is support-free. Check supports, overhangs, orientation, brim/adhesion, shell thickness and minimum feature sizes in your slicer. The readiness guide provides first-pass geometry/fit warnings, not a full manufacturing guarantee. For a physically useful mirror, print surface quality and a suitable reflective finish are additionally required.

## Files

`index.html` – Complete website/application (HTML, CSS, JS, WebGL renderer, STL generator in one file).

No external dependencies or telemetry.
