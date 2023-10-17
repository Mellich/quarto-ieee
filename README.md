# IEEE Transaction Quarto journal template

## Overview

`quarto-ieee` provide a [`IEEEtran`][`IEEEtran.cls`] template for [journal format](https://quarto.org/docs/journals/formats.html) with your [quarto](https://quarto.org/) documents.
`quarto-ieee` use the [`IEEEtran.cls`] document class that is used for most IEEE transaction articles.
It supports both `PDF` and `HTML` output.


[`IEEEtran.cls`]: https://ctan.org/pkg/ieeetran "Document class for IEEE Transactions journals and conferences"

## Creating a New Article

To create a new article using this format:


``` bash
quarto use template dfolio/quarto-ieee
```

This will create a new directory with an example document that uses this format.

## Using with an Existing Document

To add this format to an existing document:


``` bash
quarto add dfolio/quarto-ieee
```

Then, add the format to your document options:

``` yaml
format:
  ieee-pdf: default
```


## Usage

Most basic [`IEEEtran.cls`] command are supported.
For  these commands, there are some (few) limitations for the `HTML` output.
For PDF output, using the LaTeX command is often the solution.
\
Additionally, `quarto-ieee` template also supports the [`mhchem`](https://ctan.org/pkg/mhchem) (for chemical equation) 
and [`physics`](https://ctan.org/pkg/physics) (for flexible macros for typesetting equations) LaTeX packages 
and [Mathjax(v3) extensions](https://docs.mathjax.org/en/latest/input/tex/extensions/index.html).


For the  `HTML` output, `quarto-ieee` tries to mimic as closely as possible the layout seen on IEEEXplore^®^.

### Front Matter

Quarto's [authors and affiliations scheme](https://quarto.org/docs/journals/authors.html) are supported.
When provided, `note` is used as `thanks` in PDF output (ignored in HTML output).
Additionally, `photo` with `bio` allows generating a `IEEEbiography`, while a sole `bio` generates a `IEEEbiographynophoto` (this is used both in PDF and HTML outputs).
\
Supported entries:

- `funding` (see <https://quarto.org/docs/authoring/front-matter.html>)
- `citation` (see <https://quarto.org/docs/authoring/create-citeable-articles.html>)

Added entries:

```yaml
pageheader:
  left: Journal XXX, Month Year
  right: 'First Author et al.: Short title'
```


### Examples

The source code for a minimal sample document is given in [template.qmd](template.qmd).
You have a preview of the rendering of this basic template at [template.pdf](template.pdf) or  [template.html](template.html). \
Incomplete articles, i.e. more advanced examples, are available in the `examples` folder.



### Unsuported feature and limitations

- Several authors with same affiliation. 
  In such case use `note` and `tex-author-no-affiliation: true`
- For `HTML` output
  - The default Quarto toc is used, so the display is not the same as on IEEEXplore^®^.
  - Footnote are put at the end of document, while on IEEEXplore^®^ there are placed in the accordion.
  - Figures are not placed in the accordion.
  - IEEEXplore^®^ specifics (e.g. citation metrics, etc.)
  
:::{callout-important}
The `quarto-ieee` templates are intended to **approximate the final look and page length of the articles/papers** either in PDF output or HTML output. 
**They are NOT intended to be the final produced work that is displayed in print or on IEEEXplore^®^**.
They will help to give the authors an approximation of the number of pages and layout that will be in the final version. 
:::
