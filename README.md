# Klein — a surface without sides

An interactive 3D Klein bottle explorer, built with native WebGL and no external libraries.

© 2026 Felix Beacher

## Open the program

Download and open `index.html` in a modern browser with WebGL enabled. It works offline: no installation, server or build step is required. If using the ZIP package, extract it first.

## Explore

- **Rotate:** drag with the mouse. Rotation is unrestricted, including over the poles.
- **Zoom:** scroll, or use + / − with the scene focused.
- **Pan:** Shift-drag or right-drag.
- **Reset:** double-click the scene, press H, or choose Reset view.
- **Front / Side:** jump smoothly to a standard viewpoint.
- **Automatic rotation:** use the rotation button and speed slider. Manual dragging stops it; Space toggles it when the scene has focus.
- **Keyboard:** arrow keys rotate the focused scene.
- **Touch:** one finger rotates; two fingers pan and pinch to zoom. Touch controls are implemented but were not tested on a physical touchscreen during this review.

Choose Pearlescent for a shaded view, X-ray to reveal overlapping surface sheets, or Wire to study the parameter grid. Wire always displays grid lines, so the grid checkbox is disabled in that mode.

The cutaway moves a plane across the model. Its percentage describes the plane's progress across the model's width, not the proportion of surface area removed. At zero the whole bottle is shown; at 100% it is fully clipped. The cut surface is intentionally open and uncapped.

Adjust lighting and mesh detail to suit your display. Save image exports the current rendering as a PNG with a dark background and copyright notice.

Automatic rotation starts disabled when your system requests reduced motion.

## What you are seeing

A Klein bottle is a closed, non-orientable surface with Euler characteristic zero. It has no boundary and no globally consistent distinction between its two local sides.

This is a three-dimensional immersion. The neck must pass through the body in this representation; the sheets at that crossing are not connected to each other. The mathematical Klein bottle can be embedded without self-intersection in four dimensions.

The model samples a bottle-style parametric surface. Its periodic parameter seams close with an orientation reversal. The tube's tilt is smoothed near its joins to avoid an artificial lighting crease. Two-sided lighting is used because a Klein bottle has no globally consistent surface normal.

The highlighted loop closes after one lengthwise circuit. A continuously transported local normal reverses on returning to the starting point. The highlight marks the route; it does not animate a transported normal arrow.

The parameter grid, lighting and cutaway are visual aids. This is a fixed mathematical surface, not a physical simulation. There are no forces or time integration, so energy conservation does not apply.

## Performance and compatibility

All geometry and shaders are included in the HTML file. No fonts, images, libraries or other resources are downloaded.

Mesh settings use 16,384, 36,864 or 65,536 triangles. Geometry stays on the graphics processor until the detail setting changes. Display pixel density is capped at 2 to limit rendering cost.

Desktop review observed approximately 50 FPS on Balanced and 47 FPS on Fine; your device may differ. If WebGL is unavailable, the page displays an explanatory message. If the graphics context is interrupted, reload the file.

## Independent review

The separate critic scored round one 7.8/10. After improving the geometry join and cutaway labelling, round two passed at **8.6/10**:

- Visual appeal: 8.5/10
- Camera controls: 8.5/10
- Mathematical and rendering robustness: 9.0/10

Tests confirmed finite geometry, valid non-degenerate triangles and valid indices at all detail settings. Analytically identifying the parameter seams gives Euler characteristic zero and two triangles incident to every edge. Desktop interaction was tested; exhaustive cross-browser and physical-device touch testing were not performed.

See `REVIEW.md` for the critic's detailed findings.

## Put it online

Upload `index.html` to a new GitHub repository. In Settings → Pages, publish from the main branch and / (root). This project should have its own repository or subfolder so it does not replace your three-body simulation.

## Copyright

© 2026 Felix Beacher. No open-source licence is included.
