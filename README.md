# MS Computer Science Thesis Slides Repository

A premium, modular LaTeX Beamer repository configured for the **Moloch** theme and optimized for local typesetting (via **TeX Live** and **VS Code LaTeX Workshop**) and seamless **Agentic AI** collaboration.

---

## Repository Structure

The presentation is fully modularized to keep files lightweight and easy to manage for both humans and AI agents:

```bash
├── .agents/                      # Agentic AI Workspace Context
│   ├── project/                  # Domain specific info
│   │   ├── metadata.md           # Thesis title, advisors, RQs, vocabulary
│   │   └── slide_registry.md     # Narrative map of slide files & status
│   └── rules/                    # System instructions for LLM agents (.mdc)
│       ├── latex_rules.mdc       # General LaTeX compiling & formatting rules
│       ├── tikz_rules.mdc        # TikZ drawing & coordinate extraction guidelines
│       └── beamer_rules.mdc      # Beamer frames layout & styling constraints
├── preamble/                     # Presentation styling & packages
│   ├── packages.tex              # Global packages imports (TikZ, amsmath, etc.)
│   ├── macros.tex                # Custom math notation shortcuts
│   └── listings-setup.tex        # Code syntax highlighting styling configuration
├── sections/                     # Modular slides by chapter
│   ├── 01_introduction.tex       # Title, roadmap, basic column layouts
│   ├── 02_background.tex         # Literature benchmarks and math equations
│   ├── 03_methodology.tex        # Code snippets and framework classes
│   ├── 04_evaluation.tex         # custom coordinate TikZ diagrams
│   └── 05_conclusion.tex         # Q&A and Standout wrap-up slides
├── figures/                      # Assets and diagram graphics
│   └── tikz/                     # Complex TikZ source files (.tex)
│       ├── tensor_flow.tex       # Dimension representation vector drawing
│       └── arch_vis.tex          # Decentralized nodes flow flowchart
├── updates/                      # Research progress updates & milestone slides
│   ├── compiled_pdfs/            # Archive directory for finalized presentation PDFs
│   └── week01/                   # Week 1 progress report slides
│       ├── main.tex              # Update presentation compiler driver
│       └── figures/tikz/         # Venn diagram TikZ files for week 1
├── references.bib                # Thesis citation database (BibTeX)
├── .gitignore                    # LaTeX compilation log filtering configuration
└── main.tex                      # Central compiler entry-point
```

---

## How to Compile

This setup has been specifically formatted to compile flawlessly under **TeX Live** and **VS Code LaTeX Workshop**:

### 1. Local Compiling via VS Code LaTeX Workshop (Recommended)

1. Install **TeX Live** (or MacTeX/MikTeX) and make sure it is added to your environment `PATH`.
2. Install the **LaTeX Workshop** extension in VS Code.
3. Open `main.tex` in VS Code.
4. Saving `main.tex` (or any `.tex` file in `sections/` or `preamble/`) will automatically trigger a clean background build via `latexmk`.
5. Open the compiled PDF using the PDF viewer button in the top-right corner of VS Code (or press `Ctrl+Alt+V`).

### 2. Manual Compiling (Terminal)

If you wish to compile via terminal:

```bash
latexmk -pdf main.tex
```

To clean auxiliary files:

```bash
latexmk -c
```

---

## Co-Authoring with Agentic AIs

This repository uses the `.agents/` directory to store essential project context. Whenever you work with an AI assistant or coding agent:

1. **Instruct the agent** to read [.agents/project/metadata.md](file:///.agents/project/metadata.md) to understand the topic of your thesis, its core research questions, and domain terms.
2. **The agent will automatically adhere** to files in [.agents/rules/](file:///.agents/rules) to write clean LaTeX, preserve compiling compatibility (such as tagging listing frames as `[fragile]`), and write uniform TikZ equations.
3. Keep [.agents/project/slide_registry.md](file:///.agents/project/slide_registry.md) updated as you add or alter slides so that agents always know which files map to which section of your thesis.
