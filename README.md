# Bilingual Resume Template (EN/ZH)

A clean, one-page LaTeX resume template with built-in bilingual support (English & Chinese). Write your content once, generate both language versions from a single source file.

## Features

- **Single source, dual output** — use `\en{}` and `\zh{}` macros to write bilingual content in one `.tex` file
- **One-page, compact layout** — A4 paper, 9pt font, tight margins, professional section formatting
- **FontAwesome icons** — phone, email, GitHub, LinkedIn, homepage
- **XeTeX + CJK support** — automatic CJK font selection across Windows, macOS, and Linux
- **Simple build system** — `make en` / `make zh` / `make all`

## Quick Start

### Prerequisites

- [TeX Live](https://www.tug.org/texlive/) (full or medium) or [MacTeX](https://www.tug.org/mactex/)
- XeTeX (included in TeX Live / MacTeX)

### Build

```bash
make en     # Generate English PDF  -> resume-en.pdf
make zh     # Generate Chinese PDF  -> resume-zh.pdf
make all    # Generate both
make clean  # Remove build artifacts
```

### Customize

1. Edit `resume.tex` — replace all placeholder text (`Your Name`, `XX大学`, etc.) with your own info
2. Optionally add a photo: place your image file in the directory and uncomment the `\includegraphics` line in the header section
3. Add or remove sections as needed — each section is independent

## How Bilingual Mode Works

The template uses a compile-time flag (`\resumezh`) to switch languages:

```latex
\en{This text appears only in the English PDF}
\zh{这段文字只出现在中文PDF中}
Content outside \en{}/\zh{} appears in both versions
```

- `make en` compiles without the flag → `\en{}` is active, `\zh{}` is suppressed
- `make zh` compiles with `\def\resumezh{1}` → `\zh{}` is active, `\en{}` is suppressed

## File Structure

```
.
├── resume.tex    # Main source file (edit this)
├── resume.cls    # Document class (styling & layout)
├── Makefile      # Build commands
├── .gitignore    # Ignore LaTeX artifacts
└── README.md
```

## License

MIT
