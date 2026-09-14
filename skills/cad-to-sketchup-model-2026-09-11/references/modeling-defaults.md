# Modeling Defaults

Use defaults only when the drawing lacks a non-critical value. Record the
default in the topology contract and expose it in the topology white model.
The user's white-model confirmation accepts the visible default; do not add a
separate approval dialog.

## Allowed default

| Item | Rule |
|---|---|
| Ordinary door/window cut depth | Use actual host-wall thickness when known. Only when wall thickness is absent, use 200 mm and record `depth_basis: default_200_missing_wall_thickness`. The cut must fully penetrate the wall. |

Curtain walls are separate systems and do not use the ordinary-opening depth
default.

## No-default geometry

Do not invent standard values for:

- floor or roof outline;
- level height, ground datum, parapet, or roof profile;
- exterior/interior wall thickness;
- slab or roof thickness;
- sill, window, or door height;
- molding/cornice projection, recess, or section profile;
- canopy thickness, projection, edge form, or slope;
- material-driven projection or recess.

Obtain these from measurable plan/elevation/section/end-profile evidence, a
user-provided control object, or explicit topology correction. Missing
model-driving geometry keeps the contract `draft`, forces `candidate`, or
blocks the build.

## Cross-view conflict

Plans control XY topology, elevations control facade organization and vertical
datums, and sections control depth and construction relationships. Do not
blindly prioritize one view when they genuinely conflict. Record the conflict,
identify the affected topology IDs, and resolve it before confirmation.
