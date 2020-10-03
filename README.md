# LaTeX-Package
Personal LaTeX stylesheet which I am using to make my academic notes.

## Install
If you are using MiKTex navigate to `C:\Program Files\MiKTeX 2.9\tex\latex`; create a folder called `domh` and copy `*.sty` files into that folder.\
Now the package can be used anywhere on your computer.

## usepackage
The package name is called `DomH` and requires `amsmath` & `fancyhdr`.
```
\usepackage{amsmath,environ,fancyhdr}
\usepackage[section]{DomH}
\headertitle{My Notes}
```
### Options
There are two (mutually exclusive) options:
1. `section` - Counters reset at the start of every section.
2. `subsection` - Counters reset at the start of every subsection.

### Commands
There is a single package-altering command:
1. `\headertitle{__title__}` - Defines the string which goes in the centre of the header of each page.

### Shortcodes
I have defined some commands which act as shortcodes
| Command | Result | Shortcode for |
|---------|--------|---------------|
| `\prob` | <img src="https://latex.codecogs.com/gif.latex?\mathbb{P}" />  | `\mathbb{P}` |
| `\expect` | <img src="https://latex.codecogs.com/gif.latex?\mathbb{E}" />  | `\mathbb{E}` |
| `\var` | <img src="https://latex.codecogs.com/gif.latex?\text{Var}" />  | `\text{Var}` |
| `\cov` | <img src="https://latex.codecogs.com/gif.latex?\text{Cov}" />  | `\text{Cov}` |
| `\M` | <img src="https://latex.codecogs.com/gif.latex?\mathcal{M}" />  | `\mathcal{M}` |
| `\iid` | <img src="https://latex.codecogs.com/gif.latex?\overset{\text{iid}}{\sim}" />  | `\overset{\text{iid}}{\sim}` |

## Environments
Several environments are defined. Each is identical in structure but have different counters are text.\
- `definition`
- `example`
- `proof`
- `proposition`
- `remark`
- `theorem`

### Toggling Environments
All environments have their own associated boolean which toggles whether they appear in the final document or not.\
Use `\<environ>sfalse` to hide occurrences of an environment, and `\<environ>strue` to show occurrences. (*e.g.* `\definitionsfalse`)
