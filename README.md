# Factorio Space System Editor

**Factorio Space System Editor** is a standalone, browser-based visual editor for planning and documenting Factorio-style space systems.

It is intended for mod authors, modpack maintainers, compatibility-patch authors, and players who want to prototype stellar layouts before translating them into Factorio mod data.

The editor runs locally as a single HTML file. No installation, web server, or Factorio mod is required.

## What it can do

- Create and arrange stars, planets, moons, slipstreams, and general orbital points.
- Create independent orbit rings and attach bodies to parent objects.
- Draw and edit travel routes between nodes.
- Author route distances in kilometers or editor map units.
- Use live route-distance updates while moving connected nodes, or keep authored distances fixed.
- Display route-distance target guides with node-center caps.
- Display star-distance, solar, temperature, and contextual orbit-positioning guides.
- Store Solar power in orbit, Solar power in atmosphere, and temperature values on supported bodies.
- Use reusable Solar / Temperature models, including the built-in **Vanilla Nauvis** baseline and editable inverse-square/equilibrium settings.
- Save, load, copy, paste, import, export, and drag/drop both system JSON and Solar / Temperature model JSON.
- Generate randomized systems using the currently selected Solar / Temperature model so generated orbital distances and planetary values begin in a model-consistent state.
- Lock nodes, resize stars and orbits, reparent orbital children, and use snapping for fast layout work.
- Toggle map information overlays and guide types independently.
- Drag editor windows by their title bars so settings can stay out of the way of the map.
- Autosave the current working layout in the browser.

## Quick start

1. Download `index.html`.
2. Open it in a modern browser.
3. Use the **☰** menu to access:
   - **New** — create a named system or generate a randomized one.
   - **Edit** — edit the system, file locations, and Solar / Temperature model.
   - **Save / Open** — manage system JSON and Solar / Temperature model JSON.
   - **View** — theme, route behavior, guide visibility, and map overlays.
   - **Help** — detailed built-in usage documentation.
   - **About** — version and changelog information.
4. Build the layout visually, then export the resulting JSON for reference or reuse.

You can also drag a compatible system JSON or Solar / Temperature model JSON directly onto the editor.

## Solar / Temperature models

The editor separates orbital-solar planning from atmospheric solar and temperature references.

The default built-in model is **Vanilla Nauvis**, using:

- Solar power in orbit: **300%**
- Solar power in atmosphere: **100%**

The editor also includes an **Inverse-square / equilibrium** workflow. Editing model values switches the current model into that editable state.

Custom models can be saved, loaded, exported, imported, or drag-dropped. A loaded model becomes immediately available in the model list.

The temperature and distance references used by the editor are planning aids. They are not intended to claim that Factorio exposes a complete physical climate/orbital simulation.

## Random system generation

Random generation uses the currently active Solar / Temperature model rather than assigning arbitrary planetary values.

Generated planets receive:

- Solar power in orbit
- Solar power in atmosphere
- Temperature

Their generated stellar distances are chosen to agree with the active model's guide calculations. Generated moons receive the same values based on their actual resulting distance from the star.

Generated route distances are initialized from the generated geometry.

## JSON and local files

The editor supports two JSON families:

- **System layout JSON**
- **Solar / Temperature model JSON**

The Save / Open window provides separate tabs for each while using the same basic save/load/copy/paste workflow.

### Folder access

Modern browsers do not allow a local HTML page to silently write to arbitrary folders.

When supported by the browser, the editor can use the File System Access API after you explicitly authorize a folder. You can configure separate locations for systems and models, or select the editor's directory for both.

Typed directory paths are retained as labels, but a typed path alone cannot grant browser filesystem permission.

Browsers without direct folder access can still use ordinary download/upload, copy/paste, drag/drop, and browser-local storage.

## Useful interaction notes

- Mouse wheel: zoom.
- Drag empty map space or use WASD: pan.
- Drag a node: move it.
- Drag an orbit ring: resize it.
- Hold Shift while dragging/resizing: temporary free movement; release to snap.
- Ctrl-drag from a node: create a route.
- Double-click a node body: toggle its lock.
- Alt: toggle additional node information.
- Numeric fields support keyboard stepping and commit changes live when stepped.
- New/Edit/Save/Open/View/Help/About windows can be dragged by their title bars.

The editor contains a much more complete Help section covering snapping, orbital parenting, route guides, model behavior, JSON workflows, and keyboard controls.

## Data and privacy

The editor is a local HTML application.

It does not require an account and does not need a remote service to edit layouts. Browser autosave and locally saved models use browser storage. Direct filesystem access only occurs after the browser asks you to approve a folder.

## Development disclosure

For transparency: **Factorio Space System Editor was designed and iteratively developed by Skelly with assistance from ChatGPT by OpenAI.**

ChatGPT was used during implementation, debugging, documentation, UI iteration, and feature development. The tool's requirements, workflow decisions, testing feedback, and acceptance decisions were directed by Skelly throughout development.

## Unofficial community project

This is an unofficial community tool and is **not affiliated with or endorsed by Wube Software**.

Factorio-related names and game concepts are used to describe the tool's intended compatibility and workflow.

## Current release

Repository build: **v7.50**

The editor includes its own cumulative in-app changelog under **About → Changelog**.

## Running from GitHub Pages

The repository is intentionally structured with `index.html` at the root, so it can also be served directly with GitHub Pages.

If Pages is enabled for the repository from the default branch/root directory, the editor can be opened as a normal webpage without installing anything.

## Feedback and contributions

Bug reports, workflow feedback, and feature suggestions are welcome through GitHub Issues once enabled for the repository.

When reporting a layout or guide problem, including the exported system JSON and a screenshot of the affected editor state is especially useful.