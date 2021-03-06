# HES-SO//Master Lab report LaTeX template

A LaTeX template for HES-SO//Master Computer Science Deepening Project (PA)

Authors:

- Sylvain Julmy <sylvain.julmy@master.hes-so.ch>
- Marc Demierre <marc.demierre@master.hes-so.ch>

## Features

- Nice title page with school logos and lab info
- Header and footer with lab information
- Code highlighting with minted
- Nice default typography settings (by default the template uses lmodern fonts, but you can easily change the fonts in the preamble if needed)

## Dependencies and setup

### Dependencies

- A recent LaTeX distribution
- Biblatex with biber backend
- Python 2.7+ or 3+ and pygments (for the minted code highlighting package)

### Setup on OSX

1. Install a LaTeX distribution, like MacTex (https://tug.org/mactex/). Make sure the bin directory is in your `PATH`.
2. Upgrade your LaTeX distribution. With MacTex, this can be done using the built-in "TeXLive Utility" software.
3. Python is provided by default on OSX (we recommend using homebrew to get the latest version though), you just need to install the pygments package:

        pip install pygments

### Setup on Windows

1. Install a LaTeX distribution, like MiKTeX (http://miktex.org/). Make sure the bin directory is in your `PATH`.
2. Install the biber package
3. Install Python from https://www.python.org/downloads/windows/. Be sure to check the PATH option in the installer.
4. Install the pygments package

        pip install pygments

### Setup on Linux

If you use Linux, you're used to not having precise instructions. Just do it!

More seriously, the only pain point is probably the old package versions if you use an inferior distribution whose repository has an old version of TeXLive. We recommend to install TexLive manually in this case, or to use Arch.

For Archlinux :

        yaourt -S texlive-bin
        yaourt -S texlive-core
        yaourt -S texlive-latexextra
        yaourt -S texlive-bibtexextra

For Ubuntu 12.04+ users, this repository might be useful:

https://github.com/scottkosty/install-tl-ubuntu/

## Getting started

### General steps

1. Install the dependencies (see previous section)
2. Clone this repository, go to the directory where you want to create a report and use the `getreport.py` script to generate it.
3. Write your report
4. Build the PDF (see below)

### Building using the command line

A Makefile is provided so you can just use `make` to build the PDF. A `make clean` command will delete all the pdflatex build files exept the pdf and the `make clean_all` will delete all of them.

### Building using the Texmaker IDE

Use this configuration for the quick build:

    pdflatex -shell-escape -synctex=1 -interaction=nonstopmode %.tex|pdflatex -shell-escape -synctex=1 -interaction=nonstopmode %.tex

## Contributing

Do not hesitate to make a pull request if you have useful additions/corrections for this template. You can also post an issue if you find a bug or want to suggest an improvement.

The followin contributions would be welcome:

- Separation in several files (WIP):
    * `preamble.tex`: package imports and configuration
    * (done) `report.tex`: title page and content
