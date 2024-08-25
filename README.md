# tpack

Custom LaTeX packages for applications below:

- [cv](cv/tpack.sty)
- [document](document/tpack.sty)
- [letter](letter/tpack.sty)
- [report](report/tpack.sty)

## installation

### Tex Live

Required for LaTeX interpretation and PDF generatation.

#### Linux

Run the following:

```bash
sudo apt-get install texlive-full
```

If terminal stucks in an infinit loop try hitting enter as explained on [StackOverFlow](https://askubuntu.com/questions/956006/pregenerating-context-markiv-format-this-may-take-some-time-takes-forever).

> Run `tex --version` to check [TeX Live](https://www.tug.org/texlive/) installation.

#### Windows

Install [MiKTeX](https://miktex.org/howto/install-miktex).

### VSCode Setup

Install VSCode [LaTex Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop).

#### Configuration

Open VSCode settings with `ctrl + ,` and:

- set `LaTex Auto Build: Run` to `never`;
- set `LaTex Auto Clean: Run` to `onBuilt`;

Recommeded enviroment setting:

- set VSCode `Files: Auto Save` to `afterDelay`;
- set VSCode `Files: Auto Save Delay` to `100`;
- search `Editor: Rulers`, open settings.json file and add:

```json
"editor.rulers": [
    80, 100
],
```

## Usage

### Package Import

Add desired package with:

```latex
\usepackage{tpack/package_folder/package_name}
```

### PDF Generation

Main commands:

- `ctrl + alt + b`: generate PDF;
- `ctrl + alt + v`: open generated PDF;
