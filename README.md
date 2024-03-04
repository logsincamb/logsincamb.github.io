# README

This is a website for the Logarithmic Moduli Theory Conference in Cambridge. I decided to use the julia-based static site generator [Franklin](https://franklinjl.org/) since I was already familiar with it; though this is definitely overkill for a simple website like this.

## Franklin Usage

### Installation

See [the official quick start tutorial](https://franklinjl.org/). TLDR (assuming you're on a Unix based machine):

1. Install julia with the following command: `curl -fsSL https://install.julialang.org | sh`
1. Enter the julia interactive environment, enter the pkg environment and install Franklin: 
  - Enter `julia` <Enter>
  - Press `]` to enter the pkg REPL
  - Add Franklin with `add Franklin`

### Generate the site

Navigate to the base directory of the site in your CLI. You should see the directories `_assets`, `_css`, `_layout`, etc. Enter the julia interactive environment with `julia` and then enter
```bash
julia> using Franklin

julia> serve()
```
That's it.
