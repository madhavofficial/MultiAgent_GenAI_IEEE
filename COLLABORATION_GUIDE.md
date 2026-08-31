# LaTeX Collaboration Guide (VS Code + GitHub)

This repository provides an Overleaf-free collaborative workflow for writing and editing research papers with LaTeX, VS Code, and GitHub.

---

## 🚀 Quick Start for Collaborators

### 1. Requirements & Tools
- **Editor**: [Visual Studio Code](https://code.visualstudio.com/)
- **VS Code Extension**: [LaTeX Workshop (`James-Yu.latex-workshop`)](https://marketplace.visualstudio.com/items?itemName=James-Yu.LaTeX-Workshop)
- **Local TeX Engine (Optional for offline preview)**:
  - **macOS**: `brew install --cask mactex-no-gui` or `brew install --cask basictex`
  - **Ubuntu / Debian**: `sudo apt install texlive-latex-extra texlive-science latexmk`
  - **Windows**: [MiKTeX](https://miktex.org/) or TeX Live.

*(Note: Even without a local TeX installation, GitHub Actions compiles the PDF automatically on every commit/PR).*

---

## ⚡ VS Code Workflow & SyncTeX

1. **Open Project**: Open the repository folder in VS Code (`code .`).
2. **Build Document**:
   - Shortcut: `Cmd + Option + B` (macOS) or `Ctrl + Alt + B` (Windows/Linux).
   - Auto-builds on file save (`Cmd + S`).
3. **Side-by-Side PDF Preview**:
   - Shortcut: `Cmd + Option + V` (macOS) or `Ctrl + Alt + V` (Windows/Linux).
4. **SyncTeX Navigation**:
   - **TeX ➔ PDF**: Place your cursor anywhere in `main.tex` and press `Cmd + Option + J` (macOS) / `Ctrl + Alt + J` (Windows/Linux).
   - **PDF ➔ TeX**: `Cmd + Click` (macOS) / `Ctrl + Click` (Windows/Linux) anywhere inside the PDF preview to jump to the corresponding LaTeX source line.

---

## 🤖 Automated CI/CD PDF Compilation (GitHub Actions)

- Every `git push` or Pull Request automatically triggers `.github/workflows/compile-latex.yml`.
- **Download Latest PDF**:
  - Go to your repository on GitHub ➔ **Actions** tab ➔ Click on the latest workflow run ➔ Download the `MultiAgent_GenAI_IEEE_Paper` artifact.
  - Pushes to `main` also update the **Releases** page (`/releases/tag/latest`) with direct download of `main.pdf`.

---

## 🤝 Best Practices for Git + LaTeX Collaboration

1. **Semantic Line Breaks (One Sentence Per Line)**:
   - Always start each new sentence on a new line in LaTeX source.
   - LaTeX treats single newlines as regular spaces in the compiled PDF.
   - *Why?* Git diffs will show exact sentences modified rather than highlighting entire 50-line paragraphs, making code reviews and merge resolution effortless.
2. **Branching Strategy**:
   - Create feature/section branches (e.g., `feature/methodology`, `edit/intro-refinements`).
   - Open Pull Requests on GitHub for peer review and comments before merging into `main`.
3. **Reviewing in GitHub PRs**:
   - Reviewers can leave inline comments and suggest edits directly in GitHub's PR diff viewer.
