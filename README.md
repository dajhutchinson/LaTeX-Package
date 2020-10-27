# LaTeX-Package
Personal LaTeX stylesheet which I am using to make my academic notes.

## Install
If you are using MiKTex navigate to `C:\Program Files\MiKTeX 2.9\tex\latex`; create a folder called `domh` and copy `*.sty` files into that folder.\
Now the package can be used anywhere on your computer.

## usepackage
The package name is called `DomH` and requires `amsmath`,`environ`,`bbm` & `fancyhdr`.
```
\usepackage{amsmath,environ,fancyhdr,bbm}
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
| `\corr` | <img src="https://latex.codecogs.com/gif.latex?\text{Corr}" /> | `\text{Corr}` |
| `\M` | <img src="https://latex.codecogs.com/gif.latex?\mathcal{M}" />  | `\mathcal{M}` |
| `\F` | <img src="https://latex.codecogs.com/gif.latex?\mathcal{F}" />  | `\mathcal{F}` |
| `\iid` | <img src="https://latex.codecogs.com/gif.latex?\overset{\text{iid}}{\sim}" />  | `\overset{\text{iid}}{\sim}` |
| `\reals` | <img src="https://latex.codecogs.com/gif.latex?\mathbb{R}" />  | `\mathbb{R}` |
| `\nats` | <img src="https://latex.codecogs.com/gif.latex?\mathbb{N}" />  | `\mathbb{N}` |
| `\ints` | <img src="https://latex.codecogs.com/gif.latex?\mathbb{Z}" />  | `\mathbb{Z}` |
| `\I` | <img src="https://latex.codecogs.com/gif.latex?\mathcal{I}" />  | `\mathcal{I}` |
| `\X` | <img src="https://latex.codecogs.com/gif.latex?\pmb{X}" />  | `\pmb{X}` |
| `\proved` | <img src="https://latex.codecogs.com/gif.latex?\square" />  | `$\hfill\square$` |
| `\indexed` | <img src="https://latex.codecogs.com/gif.latex?\mathbbm{1}" />  | `$\mathbbm{1}$` |
| `\argmin` | <img src="https://latex.codecogs.com/gif.latex?\text{argmin}" />  | `$\text{argmin}$` |
| `\argmax` | <img src="https://latex.codecogs.com/gif.latex?\text{argmax}" />  | `$\text{argmax}$` |

## Environments
Several environments are defined. Each is identical in structure but have different counters are text.\
- `definition`
- `example`
- `proof`
- `proposition`
- `remark`
- `theorem`
- `question` Takes the question name as a parameter `\begin{question}{6b)}\end{question}`.
- `answer` Takes the question name as a parameter `\begin{answer}{6b)}\end{answer}`.

### Toggling Environments
All environments have their own associated boolean which toggles whether they appear in the final document or not.\
Use `\<environ>sfalse` to hide occurrences of an environment, and `\<environ>strue` to show occurrences. (*e.g.* `\definitionsfalse`)


## Snippets
Here is some code for the `snippets.cson` to make creating my custom environments much quicker.
```
'.text.tex.latex':
  'definition':
    'prefix': 'definition'
    'body':'\\\\begin{definition}{$1}\n\t$2\n\\\\end{definition}'
  'proposition':
    'prefix': 'proposition'
    'body':'\\\\begin{proposition}{$1}\n\t$2\n\\\\end{proposition}'
  'remark':
    'prefix': 'remark'
    'body':'\\\\begin{remark}{$1}\n\t$2\n\\\\end{remark}'
  'theorem':
    'prefix': 'theorem'
    'body':'\\\\begin{theorem}{$1}\n\t$2\n\\\\end{theorem}'
  'example':
    'prefix': 'example'
    'body':'\\\\begin{example}{$1}\n\t$2\n\\\\end{example}'
  'proof':
    'prefix': 'proof'
    'body':'\\\\begin{proof}{$1}\n\t$2\n\\\\end{proof}'
  'answer':
    'prefix': 'answer'
    'body':'\\\\begin{answer}{$1}\n\t$2\n\\\\end{answer}'
  'question':
    'prefix': 'question'
    'body':'\\\\begin{question}{$1}\n\t$2\n\\\\end{question}'
  'partialderivative':
    'prefix': 'partialderivative'
    'body':'\\\\frac{\\\\partial $1}{\\\\partial $2}$3'
  'texttt':
    'prefix': 'tt'
    'body':'\\\\texttt{$1} $2'
```
To use these snippets type the *environment name* then press *tab* (e.g. `definition` + `tab`). This will generate the environment code and place the cursor in the *name* location.
