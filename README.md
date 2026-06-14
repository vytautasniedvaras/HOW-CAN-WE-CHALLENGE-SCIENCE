# HOW CAN WE CHALLENGE SCIENCE

The BYO title type projected onto an **invisible, mouse-driven cube**.

The three title lines are rendered flat to a transparent texture on a finely
subdivided plane. A custom GLSL vertex shader ray-casts every vertex along the
view axis into an invisible rotating cube and lifts the vertices that fall
inside the silhouette onto the cube's front faces — so the type warps as if
projected onto the shape, easing seamlessly back to flat at the edges. A
derivative-based facing fade in the fragment shader removes the stretched
edge-on "wall" triangles at the silhouette, keeping the text clean.

## Motion
- Move the mouse and the cube **heads toward** the motion (with a build-up).
- Stop moving and it **keeps coasting** along the last heading axis — a slow
  idle spin that never fully stops, decaying back from the active heading.

## Interaction
- **Hover a line and swipe horizontally** to change its word. The first two
  lines share the noun (they change together); the bottom line changes its
  verb on its own. Every word change also flips the gizmo to a different widget.
- Drag the **gizmo** to move / rotate / scale the invisible cube.
- Keys: **W** move · **E** rotate · **R** scale · **Space** pause · **H** toggle the control panel.

## Files
- `index.html` — loads `word-pairings.js` (open over a local server or file://).
- `codepen.html` — single self-contained file (word data inlined) for pasting straight into CodePen.

Built with [three.js](https://threejs.org/) r128.
