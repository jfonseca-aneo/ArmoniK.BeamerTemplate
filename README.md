# LaTeX Beamer template for ArmoniK presentations

This repository contains a beamer template with a custom ANEO inspired theme and a build systempowered by [`just`](https://github.com/casey/just). It supports automatic compilation using `latexmk` if installed, or falls back to `pdflatex` otherwise.

## Requirements

- `just` command runner
- LaTeX distribution (e.g.; TeX Live)
- Optional: `latexmk` for smarter compilation

## Usage

The example directory provides a sample presentation using the custom theme. The directoy contains two files: the  `.tex` file defining the slides itself and a `justfile` to compile it. The later prepends to the environment variable `TEXINPUTS`  the path of our custom tbeamer theme, which is set via the variable:

```make

THEME_DIR := $(realpath "../aneotheme")

```

If the `latexmk` utility is available, it will be used automatically for a smarter compilation. Otherwise the `justfile` employs `pdflatex`.

If you wish to start a new presentation a copy of the example directory is a good startingpoint, you may create it in at the same level as the example directory, in which case the copied `justfile` should correctly compile your presentation. If you choose to create a new presentation in a different arbitrary location, you will need to adapt the value of `THEME_DIR` to point to the location of the custom theme.
