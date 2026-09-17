
# LaTeX Resume Template ([Preview here](/resume.pdf))

A modular LaTeX resume template where configuration, reusable commands, and individual CV sections are split into separate files.

## Structure

```text
.
├── resume.tex
├── config.tex
├── commands.tex
└── sections/
    ├── header.tex
    ├── experience.tex
    ├── education.tex
    ├── awards.tex
    ├── skills.tex
    ├── volunteer.tex
    ├── projects.tex
    ├── research.tex
    └── publications.tex
```

### `resume.tex`

The main document. It defines the document class and loads all other files in the desired order.

Sections can easily be reordered, removed, or added by changing the corresponding `\input` lines:

```latex
\input{sections/experience}
\input{sections/education}
\input{sections/skills}
```

To hide a section, simply remove or comment out its line:

```latex
% \input{sections/publications}
```

### `config.tex`

Contains the general LaTeX configuration, packages, fonts, margins, and visual styling.

### `commands.tex`

Contains reusable commands used throughout the resume, such as:

```latex
\resumeSubheading
\resumeItem
\resumeProjectHeading
```

These commands keep the formatting consistent across all sections.

### `sections/`

Each part of the resume lives in its own file. Section files contain only the content for that section and do not need their own `\begin{document}` or `\end{document}`.

For example:

```latex
\section{Experience}

\resumeSubHeadingListStart
    ...
\resumeSubHeadingListEnd
```

## Compiling

Compile `resume.tex`, not the individual section files.

With `latexmk`:

```bash
latexmk -pdf resume.tex
```

To remove generated build files:

```bash
latexmk -c
```

## Customizing

1. Edit the content inside `sections/`.
2. Reorder sections in `resume.tex`.
3. Adjust fonts, margins, and other styling in `config.tex`.
4. Modify or add reusable formatting commands in `commands.tex`.
5. Comment out sections that are not needed for a particular application.

This makes it easy to maintain multiple CV variants while keeping the underlying design consistent.
