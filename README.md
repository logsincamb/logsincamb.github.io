# README

This is a website for the Logarithmic Moduli Theory Conference in Cambridge. I decided to use the julia-based static site generator [Franklin](https://franklinjl.org/) since I was already familiar with it; though this is definitely overkill for a simple website like this. Google sites or vanilla Jekyll would've worked just as well.

## Franklin Usage

### Installation

See [the official quick start tutorial](https://franklinjl.org/). TLDR (assuming you're on a Unix based machine):

1. Install julia with the following command: `curl -fsSL https://install.julialang.org | sh`
1. Enter the julia interactive environment, enter the pkg environment and install Franklin: 
  - Enter `julia` <Enter>
  - Press `]` to enter the pkg REPL
  - Add Franklin with `add Franklin`
You should now have Franklin and julia installed.

### Generate the site

Navigate to the base directory of the site in your CLI. You should see the directories `_assets`, `_css`, `_layout`, etc. Enter the julia interactive environment with `julia` and then enter
```bash
julia> using Franklin

julia> serve()
```
That's it.

### Site structure

Franklin converts markdown (`.md`) files into HTML files. For a detailed description of how this works, see [Franklin page structure](https://franklinjl.org/workflow/structure/) and to read about Franklin's specific markdown syntax [see the docs](https://franklinjl.org/syntax/markdown/). The CSS can be customized in `_css/`, basic HTML copied across all pages can be modified in `_layout/` and basic site assets can be modified in `_assets/`. The landing page is `index.md` in the base directory and all other pages are found in `pages/`.

The generated site, complete with HTML files is placed in the directory `__site`. These files are pushed to the git branch called `gh-pages`.

### Potentially useful features

**Math**: Write math inline using pairs of `$`: `$\mathbb C$` for instance. Use `\begin{align*}\end{align*}` for display mode math. Besides `tikz` and `tikz-cd` most major libraries you'd want for typesetting math are supported by default. Potentially useful for putting talk abstracts directly on the website.

**Custom Commands and Functions**: [See the docs](https://franklinjl.org/syntax/divs-commands/#latex-like_commands) for more information. Commands can be added in individual markdown files with `\newcommand{}[]{}` and can be defined globally by inserting them in `config.md`, located in the base directory. You can also customize the generation of site content with julia functions called `hfun`. I took the liberty of writting one that will print a participant list (`/pages/participants.csv`) in alphabetical order.
