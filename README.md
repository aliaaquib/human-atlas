# Human Atlas

**An interactive 3D anatomy explorer for discovering the human body, one structure at a time.**

Human Atlas is an interactive anatomy visualization platform built with React, Three.js, and shadcn/ui. It transforms the BodyParts3D adult male reference model into **2,234 individually selectable meshes**, allowing users to explore **15 anatomical systems** and search through **3,432 named anatomical concepts** in an interactive 3D environment.

🔗 **Live Demo:** [human-atlas.aaquibali.com](https://human-atlas.aaquibali.com)

## ✨ Features

- **Interactive 3D Exploration** — Orbit, zoom, rotate, and select anatomical structures directly on the 3D model.
- **15 Anatomical Systems** — Explore different systems of the human body using individual visibility controls and preset views.
- **Exploded Anatomy View** — Separate the assembled model into a spatial inventory of its visible structures.
- **Anatomical Search** — Find structures by anatomical name or source identifier.
- **Structure Inspection** — Isolate individual structures and explore their associated details.
- **Smart Visibility Controls** — Toggle individual structures and switch between skeleton and organ presets.
- **Responsive Interface** — Compact controls and adaptable detail panels for desktop, tablet, and mobile screens.
- **Optimized Rendering** — GPU-based visibility, selection, and translation controls enable efficient rendering of thousands of anatomical structures.
- **Optional WebMCP Integration** — Expose anatomy search and inspection tools in compatible browsers, while keeping the standard interface fully functional without them.

## 🛠️ Tech Stack

- **React** — Component-based user interface
- **Three.js** — Interactive 3D rendering and anatomy visualization
- **shadcn/ui** — Reusable interface components
- **Vite** — Development server and production build tooling
- **WebMCP** — Optional browser-compatible anatomy tools

## 🧪 Validation

Run the project's validation commands before deploying changes:

```bash
npm run check
node scripts/validate-atlas.mjs
node scripts/validate-interactions.mjs
npm run build
```

The validation suite checks:

- Geometry buffers and anatomical mesh integrity
- Anatomical names and concept membership
- Exploded-layout spacing at desktop and mobile aspect ratios
- Search and structure-inspection behavior
- Tap-versus-drag interaction handling

Browser interaction checks cover selection, anatomical system controls, search, isolation, rotation, and responsive layouts, including:

- 390 × 844
- 320 × 568
- 844 × 390

The interface is designed to keep controls accessible while exploring exploded anatomy and to fit isolated structures alongside or above the details panel.

**Testing limitations:** Physical-device performance and real multitouch hardware have not been tested.

## 🧬 Anatomy Data

Human Atlas currently uses **BodyParts3D 4.0**, an adult male reference anatomy model.

| Specification | Details |
|---|---|
| Source dataset | BodyParts3D 4.0 |
| Reference model | Adult male anatomy |
| Selectable meshes | 2,234 |
| Anatomical systems | 15 |
| Named concepts | 3,432 |
| Geometry | 2,288,268 triangles |
| Compressed geometry download | Approximately 33 MB |
| Data license | CC BY 4.0 |

The viewer preserves every source mesh while simplifying geometry for browser performance.

Anatomical meshes and named concepts are distinct: a single concept may represent multiple meshes. Descriptions also distinguish general anatomical-system context from explanations of individual organs.

The dataset represents a reference model, not every anatomical structure, individual variation, or human body type.

For full dataset credits, source links, and adaptation details, see [`public/ATTRIBUTION.md`](public/ATTRIBUTION.md).

## ⚙️ How It Works

Human Atlas combines optimized 3D geometry with GPU-based controls to deliver an interactive anatomy experience.

- **Batched Geometry:** Anatomical geometry is merged into batches to reduce rendering overhead.
- **GPU-Controlled Structures:** Per-structure GPU textures manage translation, visibility, and selection.
- **Accurate Picking:** Component geometry supports direct selection of individual anatomical structures.
- **Dynamic Exploded Layouts:** Only visible structures are included when arranging the exploded view.
- **Efficient Rendering:** Scene rendering updates when necessary, while orbit controls remain responsive without requiring thousands of separate draw calls.

This approach balances detailed anatomical exploration with browser performance.

## 📄 License

Human Atlas uses separate licenses for its application code and anatomical data.

- **Application Code:** [MIT License](LICENSE)
- **Anatomy Data:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

The anatomy dataset has its own licensing requirements. Preserve the required attribution and follow the applicable terms when redistributing the dataset or adapted materials.

Third-party dependencies remain subject to their respective licenses.

## ⚠️ Disclaimer

Human Atlas is an educational and visualization tool designed to support anatomy learning and exploration.

**It is not intended for medical diagnosis, treatment decisions, or surgical planning.**

## 🤝 Contributing

Issues, bug reports, and pull requests are welcome.

When reporting an issue, please include:

- Steps to reproduce the problem
- Expected and actual behavior
- Browser and operating system
- Device type and screen dimensions, where relevant

Contributions that improve accessibility, performance, anatomical exploration, and educational usability are welcome.

---

**Human Atlas** — Explore the human body in 3D, one structure at a time.

[Explore the live demo](https://human-atlas.aaquibali.com)
