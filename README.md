# tpack

Custom LaTeX packages for applications below:

- [cv](cv/tpack.sty)
- [document](document/tpack.sty)
- [letter](letter/tpack.sty)
- [report](report/tpack.sty)

## Installation

### pre-commit

> If you are using Windows, disconsider this section.

Pre-commits in a repository help enforce code quality and consistency by automatically running checks (like linters, formatters, or tests) before changes are committed.

This ensures that only code meeting certain standards is added to the project, reducing errors and improving maintainability.

In Linux open the repository main folder and run:
```bash
pre-commit -V

# pre-commit 2.17.8
```
If a version is shown, `pre-commit` is already installed. If it is not the case, installed, run:
```bash
sudo apt install pre-commit
```
Then in the repository main folder run:
```bash
pre-commit install
pre-commit --install-hooks
```
Wait until it is finished. Then run:
```bash
pre-commit run --all-files
```
All necessary auxiliary files will be created:

- .clang-format
- .cmake-format.yaml
- .isort.cfg
- .pylintrc

Then run:

```bash
sudo apt install clang-format
```

Finally, `pre-commit` is installed.

#### `pylint`

If a `pylint` warning should be ignored add:

```python
# pylint: disable=<flag-name>
...
```

If all `pylint` warnings should be ignored add:

```python
...
# pylint: skip-file
```


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

- set `LaTeX Auto Build: Run` to `never`;
- set `LaTeX Auto Clean: Run` to `onBuilt`;
- set `LaTeX Clean Subfolder: Enabled` to `true`;
- set `LaTeX LaTeX Root File: Use Sub File` to `true`;

Recommeded enviroment setting:

- set VSCode `Editor: Render Whitespace` to `trailing`;
- set VSCode `Files: Auto Save` to `afterDelay`;
- set VSCode `Files: Auto Save Delay` to `100`;
- search `Editor: Rulers`, open settings.json file and add:

```json
"editor.rulers": [
    80, 100
],
```

## Usage

### Subfiles

Using subfiles in LaTeX allows you to break a large document into smaller, manageable sections. Each section can be edited and compiled independently, improving collaboration and workflow, especially in complex projects like theses or books. It also helps in organizing content efficiently without cluttering the main document.

Project structure example:

```bash
.
├── document
│   ├── main.tex
│   └── sections
│       ├── section_1.tex
```

`main.tex` file:

```LaTeX
% main.tex
\documentclass{article}
\usepackage{../../../../tpack/document/tpack}

...
```
`section_1.tex` file:

```LaTeX
% section_1.tex
\documentclass[../main.tex]{subfiles}

...
```

With this structure is possible to build the `main.tex` from the `section_1.tex` file.

### Package Import

Add desired package with:

```latex
\usepackage{tpack/package_folder/package_name}
```

### PDF Generation

Main commands:

- `ctrl + alt + b`: generate PDF;
- `ctrl + alt + v`: open generated PDF;
