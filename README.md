# LaTeX Resume Template

A clean, public-ready resume template based on Deedy Resume with open-source fonts and XeLaTeX support.

## Quick Start

### 1) Clone the repo

```bash
git clone <your-repo-url>
cd overleaf
```

### 2) Build the sample resume

```bash
latexmk -C main.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir=build main.tex
```

Output: `build/main.pdf`

### 3) Customize your resume

Edit `main.tex`:
- Update `\namesection` with your name and contact
- Replace content in `Education`, `Experience`, `Skills`, and `Projects`

### 4) Rebuild after edits

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir=build main.tex
```

Every build writes the generated resume to:

- `build/main.pdf`

## Keep Personal Resume Local (Untracked)

This repo is configured so `main.personal.tex` is ignored by git.

Recommended workflow:

```bash
cp main.tex main.personal.tex
```

- Keep your private version in `main.personal.tex`
- Keep `main.tex` generic/public for GitHub

## Requirements

- LaTeX distribution with XeLaTeX (MacTeX, BasicTeX, or TinyTeX)
- `latexmk`

Verify:

```bash
xelatex --version
latexmk --version
```

## Project Structure

```text
.
├── main.tex                  # Public template
├── main.personal.tex         # Local/private copy (gitignored)
├── deedy-resume-openfont.cls # Resume class
├── fonts/                    # Lato + Raleway fonts
└── build/                    # PDF and LaTeX build output
```

## What To Track In Git

- Track source files like `main.tex`, class files, fonts, and docs.
- Do not track LaTeX temporary artifacts such as `.aux`, `.log`, `.out`, `.xdv`, `.fls`, `.fdb_latexmk`, `.synctex.gz`.
- Generated `main.pdf` can be rebuilt by anyone with one command, so it is usually better to keep it untracked.

## License

Licensed under Apache 2.0. See [LICENSE.txt](LICENSE.txt).

