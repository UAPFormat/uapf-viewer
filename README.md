# uapf-viewer

Web UI **playground & viewer** for `.uapf` packages.

Upload a UAPF archive, validate it, and explore its contents:

- Inspect manifest, agents, integration metadata.
- View BPMN / DMN / CMMN diagrams (where supported).
- See how MCP tools and A2A schemas are declared.

This repo is intended primarily for **developers, architects, and reviewers** of UAPF models.

---

## Features (planned / current)

- **File upload**
  - Drag-and-drop or file chooser for `.uapf` archives.

- **Schema validation**
  - Runs validation via the TypeScript SDK (`uapf-typescript`).
  - Shows pass/fail status and detailed error messages.

- **Package explorer**
  - Tree view for:
    - `manifest.json`
    - `agents/` (roles, capabilities, bindings)
    - `decisions/` (DMN & glossary)
    - `integration/` (MCP tools, A2A schemas, APIs)
    - `metadata/`

- **Diagram preview** (where implemented)
  - BPMN / CMMN rendered via a browser modeller library.

- **Developer-friendly**
  - Useful for debugging `.uapf` packages during modelling and engine integration.

---

## Running locally

```bash
git clone https://github.com/UAPFormat/uapf-viewer.git
cd uapf-viewer
npm install
npm run dev    # or npm start / npm run preview, depending on tooling
```

Then open the printed localhost URL in your browser.

> The viewer is a **static web app** – it does not execute business logic from
> the `.uapf` package; it only validates and visualizes.

---

## Architecture

- Built in **TypeScript** on top of:
  - [`uapf-typescript`](https://github.com/UAPFormat/uapf-typescript) for parsing/validation.
  - A diagram library (e.g. BPMN/DMN/CMMN modelers) for visualization.

All processing can be implemented to happen **in the browser**; no `.uapf` file contents need to be sent to external services unless explicitly configured.

---

## Roadmap

- Richer diagram browsing (sub-processes, drill-down).
- Side-by-side JSON and diagram views.
- Integration with conformance fixtures for demo purposes.
- Optional “shareable permalink” mode for public examples.

---

## License

MIT – see [`LICENSE`](LICENSE) if present, or follow org-wide license.

