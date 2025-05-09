# LaTeX Beamer template for ArmoniK presentations

This repository contains a beamer template with a custom ANEO inspired theme and a build systempowered by [`just`](https://github.com/casey/just). It supports automatic compilation using `latexmk` if installed, or falls back to `lualatex` otherwise.

## Requirements

- `just` command runner
- LaTeX distribution (e.g.; TeX Live)
- lualatex to be able to use the Poppins and Lexend Deca fonts
- Optional: `latexmk` for smarter compilation

## Usage

The example directory provides a sample presentation using the custom theme. The directoy contains two files: the  `.tex` file defining the slides itself and a `justfile` to compile it. The later prepends sets two environment variables:

 - `TEXINPUTS` with the path of our custom beamer theme, which is set via the variable:
 - `OSFONTDIR` with the path of the fonts used by the theme.

```make

THEME_DIR := $(realpath "../aneotheme")
FONTS_DIR := THEME_DIR + "/fonts"

```

If the `latexmk` utility is available, it will be used automatically for a smarter compilation. Otherwise the `justfile` employs `pdflatex`.

If you wish to start a new presentation a copy of the example directory is a good startingpoint, you may create it in at the same level as the example directory, in which case the copied `justfile` should correctly compile your presentation. If you choose to create a new presentation in a different arbitrary location, you will need to adapt the value of `THEME_DIR` to point to the location of the custom theme.
