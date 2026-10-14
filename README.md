# 📐 BookCalculus — LaTeX Template for a Calculus Textbook

## Overview

**BookCalculus** is a professional LaTeX template for creating Calculus textbooks and course notes. The editorial design draws inspiration from major market textbooks (Stewart, Anton, Thomas), with a modern layout, per-chapter color system, and ready-to-use math environments.

---

## What's Included

| File | Description |
|---|---|
| `calculus.tex` | Full template in **English** |
| `calculus.pdf` | Compiled demo PDF (EN) |
| `README.md` | Documentation and usage guide |
| `LICENSE` | Usage and redistribution terms |

[View the compiled PDF demo](calculus.pdf)

---

## Template Content

The template demonstrates **4 complete chapters**:

1. **Limits and Continuity** — Formal definition (ε-δ), one-sided limits, theorems, continuity
2. **Derivatives** — Rate of change, differentiation rules, chain rule, derivative table
3. **Applications of Derivatives** — Extrema, derivative tests, optimization, L'Hôpital's Rule
4. **Indefinite Integrals** — Basic integrals, substitution, integration by parts

Each chapter includes: an opening with topic list, step-by-step lessons, definitions, theorems, solved examples, numbered exercises, and a quick answer key.

---

## Requirements

- **LaTeX Distribution:** TeX Live 2022+ or MiKTeX 22+
- **Compilation Engine:** `pdflatex` with the `-shell-escape` flag
- **Required Packages:** All included in standard distributions:
  - `tcolorbox`, `pgfplots`, `tikz`, `fancyhdr`, `titlesec`, `titletoc`
  - `amsmath`, `amssymb`, `mathtools`, `enumitem`, `multicol`
  - `colortbl`, `booktabs`, `tasks`, `qrcode`, `microtype`

---

## How to Compile

```bash
# Compile twice to correctly generate the table of contents
pdflatex -shell-escape calculus.tex
pdflatex -shell-escape calculus.tex
```

> ⚠️ The `-shell-escape` flag is required by the `qrcode` package.

---

## Available Environments

### Content Boxes

```latex
\begin{definition}{Optional Title}
  Definition text...
\end{definition}

\begin{theorem}{Theorem Name}
  Statement...
\end{theorem}

\begin{example}{1.1}
  Problem and solution...
\end{example}

\begin{caution}
  Important warning...
\end{caution}

\begin{didyouknow}
  Extra context...
\end{didyouknow}

\begin{lesson}{Lesson Title}
  Step-by-step content...
\end{lesson}

\begin{exercise}[Optional Subtitle]
  Exercise statement...
\end{exercise}

\begin{answerkey}
  \textbf{1a)} answer \par
  \textbf{1b)} answer
\end{answerkey}
```

### Utility Commands

```latex
% Highlighted formula box (orange)
\formula[Optional Label]{f'(a) = \lim_{h\to 0}\frac{f(a+h)-f(a)}{h}}

% Highlighted numerical result
\result{$x = 10\,\text{cm}$}

% Numbered step
\step{1}{Analyze the table of values below...}

% Topic icon
\topic{2}{Formal definition ($\varepsilon$-$\delta$)}

% Decorative section divider
\secbar

% Pro/con comparison (two-column)
\procon{Pros}{text...}{Cons}{text...}

% QR code with caption
\qrbox{https://site.com}{Caption text}
```

---

## Color Customization

Each chapter can have its own color — just call `\setChapColor` at the beginning of each chapter:

```latex
% Blue chapter
\setChapColor{Cap1Blue}{LightBlue}
\chapter{Limits and Continuity}

% Orange chapter
\setChapColor{Cap2Orange}{LightOrange}
\chapter{Derivatives}
```

The predefined colors are:

| Name | Hex Code | Suggested Use |
|---|---|---|
| `Cap1Blue` | `#1E9ED7` | Chapter 1 |
| `Cap2Orange` | `#F07E26` | Chapter 2 |
| `Cap3Green` | `#5BB85D` | Chapter 3 |
| `Cap4Purple` | `#7C5CBF` | Chapter 4 |

You can redefine any color in the preamble:

```latex
\definecolor{Cap1Blue}{HTML}{2C3E50}  % your custom color
```

---

## Adapting the Template

### To create a new chapter:
1. Call `\setChapColor{Color}{LightColor}` to set the chapter palette
2. Use `\chapter{Name}` and `\markboth{...}{}`
3. Open with `\begin{multicols}{2}...\end{multicols}` for the intro
4. Use `\secbar` to separate sections
5. Add sections with `\section{...}`, lessons, theorems, examples, and exercises

### To customize the cover page:
- Edit the `\begin{titlepage}...\end{titlepage}` block
- Modify text in TikZ nodes (title, subtitle, chapter list)
- Adjust background colors by changing `\fill[Cap1Blue]`

---

## Support

Questions about LaTeX? Check out:
- [Overleaf Documentation](https://www.overleaf.com/learn)
- [CTAN Package Index](https://www.ctan.org)
- [TeX Stack Exchange](https://tex.stackexchange.com)
