# OpenCollage (o9e) Documentation

Presentation materials for **OpenCollage (o9e)** -- a universal open standard for AI agent orchestration.

OpenCollage provides a framework-agnostic adapter layer so that agents from any framework (AutoGen, CrewAI, LangGraph, or custom SDKs) can participate as first-class nodes in a shared execution DAG.

## Repository Structure

```
.
├── Makefile                  # Root build (delegates to slides/)
└── slides/
    ├── beamerthemeRedHat.sty  # Red Hat-branded Beamer theme
    ├── redhat-logo.png        # Logo asset
    ├── fonts/                 # Red Hat Display font family (.otf)
    ├── Makefile               # Delegates to presentation subdirectories
    └── inception/             # Inception presentation
        ├── 000-opencollage.tex  # Main document (includes all sections)
        ├── 001-*.tex .. 017-*.tex  # Section files
        └── Makefile
```

## Prerequisites

- **XeLaTeX** (or LuaLaTeX) -- required by the theme for `fontspec` / Red Hat Display fonts
- Standard LaTeX packages: `beamer`, `tikz`, `fontawesome5`, `listings`, `hyperref`

## Build

```bash
# Build all presentations
make

# Build a single presentation
cd slides/inception && make

# Clean build artifacts
make clean

# Deep clean (removes PDFs too)
make clobber
```

The output PDF is generated as `slides/inception/OpenCollage-Agent-Orchestrator.pdf`.

## Adding a New Presentation

1. Create a new subdirectory under `slides/` with its own `Makefile`
2. Symlink (or copy) `beamerthemeRedHat.sty`, `redhat-logo.png`, and `fonts/` into it
3. Add the subdirectory name to `SUBDIRS` in `slides/Makefile`

## Presentation Topics

The **inception** presentation covers:

- The AI agent framework fragmentation problem
- OpenCollage core architecture and Kubernetes analogy
- Use cases: security incident response, SDLC pipelines
- Declarative pipeline definitions (YAML DAGs)
- State management, observability, and communication protocols
- Framework-agnostic execution via the four-method adapter contract
- Agent registry, deployment automation, and supply chain security
- Defensive patent candidates
- Governance, roadmap, and call to action
