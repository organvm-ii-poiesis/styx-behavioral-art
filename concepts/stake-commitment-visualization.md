# Stake and Commitment Visualization

## Premise

Every stake in the Styx system carries a numerical weight, a temporal duration, and an eventual outcome. These three dimensions -- magnitude, time, resolution -- are sufficient to generate rich visual compositions. The goal is not informational dashboards but data art: pieces that convey the emotional texture of commitment and risk.

## Visual Language

### Force-Directed Stake Graphs

A d3.js-style force simulation where each active stake is a node. Node radius scales with stake amount. Color saturation encodes time remaining -- deeply saturated nodes are fresh commitments, desaturated ones are approaching expiry. Edges connect staker to auditor, and their thickness reflects the number of completed audit cycles between the pair.

The result is an evolving constellation. Dense clusters reveal trust networks. Isolated bright nodes signal high-stake newcomers. The graph breathes -- nodes drift apart as commitments expire, snap together when new audit relationships form.

### Commitment Duration as Horizon Line

A second visualization treats commitment duration as a landscape. Each commitment is a vertical band whose height is proportional to its duration and whose width reflects stake amount. Bands are arranged chronologically left to right, creating a skyline of obligation. Completed commitments fade to a warm amber; defaulted ones leave dark voids.

Over time, the skyline accumulates into a geological cross-section -- layers of kept promises and broken ones, readable as a history of collective behavior.

### Outcome Particles

When a stake resolves (audit passed, commitment fulfilled, or default), the event spawns a particle burst. Successful resolutions emit upward-drifting particles in the staker's color. Defaults scatter downward in gray. These particles persist, slowly accumulating into a sediment layer at the bottom of the canvas -- a residue of all past accountability events.

## Technical Direction

- **Rendering:** Canvas or WebGL for particle systems; SVG for force graphs where interaction matters more than particle count.
- **Data source:** Consumes snapshots from the Styx theory models (ORGAN-I). Initially synthetic data generated from the behavioral economics parameters; eventually live chain data from the ORGAN-III product.
- **Interactivity:** Hover reveals stake metadata. Click isolates a node's audit network. Time slider replays the commitment history.

## Aesthetic Intent

The visualizations should feel organic rather than clinical. Stake networks resemble mycorrhizal webs. Commitment skylines evoke stratigraphy. The overall impression should be that accountability is a living system -- growing, decaying, regenerating -- not a static ledger.

## Open Questions

- At what scale does the force graph become illegible? Can hierarchical clustering (auditor clusters within organ clusters) maintain readability at thousands of nodes?
- Should defaulted stakes be visually punitive (red, sharp) or neutral (gray, fading)? The theory is non-moralistic, but art carries emotional weight regardless of intent.
- How to handle the cold-start problem -- early networks will be sparse. Does sparsity itself become an aesthetic feature (loneliness of early adopters)?
