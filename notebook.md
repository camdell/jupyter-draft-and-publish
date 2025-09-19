---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.17.3
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# My Notebook

We made our first notebook, using features of Jupyter & Jupytext

## Python Code

```{code-cell} ipython3
3 + 10
```

```{code-cell} ipython3
x = 3
y = 4

x ** y
```

### Parse & Visualize Data

In this section, we download a dataset with Polars and visualize it with Matplotlib

```{code-cell} ipython3
import polars as pl

df = pl.read_csv(
    "https://gist.githubusercontent.com/slopp/ce3b90b9168f2f921784de84fa445651/raw/4ecf3041f0ed4913e7c230758733948bc561f434/penguins.csv",
    null_values="NA",
)
df.head()
```

```{code-cell} ipython3
import matplotlib.pyplot as plt

fig, ax = plt.subplots(figsize=(6, 4))

ax.scatter(df["flipper_length_mm"], df["body_mass_g"], s=20)
ax.set_title("Body Mass and Flipper Length are Correlated!")
ax.set_ylabel("Body Mass (g)")
ax.set_xlabel("Flipper Length (mm)");
```

## Common Mark Markdown Features

### Bullet Points

unordered bullet point
- bullet points
- 2nd bullet point
    - indented point

+++

ordered/numbered bullet points

1. bullet points
2. 2nd bullet pint
    1. sub point

+++

### Typography

**Bold Text** → text surrounded by 2 asterisks on either side

*itaicized text* → text surrounded by 1 asterisk on either side

+++

### Hyperlinks & References

https://en.wikipedia.org/wiki/Project_Jupyter

[This is a link to Jupyter’s Wiki Page](https://en.wikipedia.org/wiki/Project_Jupyter)

![Project Jupyter’s Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Jupyter_logo.svg/207px-Jupyter_logo.svg.png)

+++

### MathJax 
(Not supported by Common Mark Standard)

y = 1/2 * x + b

$y = 1/2 * x + b$

$y = \frac{1}{2}x + b$

+++

## MyST Features

### Typography

\{…\}\`…\`

{del}`this is struck through`

{u}`this is underlined`

Today is the 19{sup}`th`

Water is H{sub}`2`O

The shortcut to copy text is {kbd}`Ctrl` + {kbd}`C`

{abbr}`DUTC (Don’t Use This Code)`

+++

### Quotations

> This is a quote, it is valid markdown

---

> This is a quote, it is valid markdown
>
> -- Cameron Riddell

+++

### Definition Lists

Water
: Something you drink to stay alive

Air
: Something you breathe to stay alive

+++

### Footnotes

Here is my footnote[^footnote-1] and another footnote here: [^footnote-2]

[^footnote-1]: first footnote
[^footnote-2]: second footnote

+++

### Directives

:::{note}
Some text that is very important
:::

+++

:::{image} https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Jupyter_logo.svg/207px-Jupyter_logo.svg.png
:alt: Project Jupyter's Logo
:width: 100px
:align: center
:::

+++

:::{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Jupyter_logo.svg/207px-Jupyter_logo.svg.png
:label: my-fig
:alt: Project Jupyter's Logo
:width: 100px
:align: center

This is a caption for a figure
:::

+++

### Cross References

Remember the [common mark syntaxes](#common-mark-markdown-features) we've seen?

### References

This is in text citation for [Harris et. Al, 2020](doi:10.1038/s41586-020-2649-2)

According to {cite:t}`numpy`, NumPy is a great tool.

Matplotlib {cite:p}`matplotlib`…
