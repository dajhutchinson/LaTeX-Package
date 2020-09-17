# LaTeX-Package
Personal LaTeX stylesheet which I am using to make my academic notes.

## usepackage
The package name is called `DomH` and requires `amsmath` & `fancyhdr`.
```
\usepackage{amsmath,fancyhdr}
\usepackage[section]{DomH}
\headertitle{My Notes}
```
### Options
There are two (mutually exclusive) options:
1. `section` - Counters reset at the start of every section.
2. `subsection` - Counters reset at the start of every subsection.

### Commands
There is a single command:
1. `\headertitle{__title__}` - Defines the string which goes in the centre of the header of each page.

## Environments
Several environments are defined. Each is identical in structure but have different counters are text.\
- `definition`
- `example`
- `proof`
- `proposition`
- `remark`
- `theorem`
