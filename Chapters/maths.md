# Maths

## Standard LaTeX

Jupyter Books allows the typesetting of mathematics using LaTeX via the MathJax package.

All standard LaTeX command can be used in the usual way. So, we can use `$...$` for inline mathematics, eg: $a^2+b^2=c^2$

or `$$...$$` for a maths block:

$$
  f(x) = ax^2+bx+c
$$


In `_config.yml` the amsmath extension has been switched on using

	parse:
      myst_enable_extensions:
        - amsmath


This enables amsmath environments, such as `equation`, `align`, `pmatrix`, etc to be used.

For example, using `equation*` gives:

\begin{equation*}
g(x) = \sin(x^2+1)
\end{equation*}

and using `align*` gives

\begin{align*}
a &= b+c\\
a &= d+e
\end{align*}

`pmatrix`, etc, can be used with or without being placed in a maths environment.

$$
\begin{pmatrix} a & b & c \\ d & e & f \end{pmatrix}
$$
And other environments are also available:

$$
H(x) = \begin{cases}
1, & x > 0 \\
0, &\text{otherwise.}
\end{cases}
$$


## Referencing Equations

There are two ways of labelling and referencing equations.

A regular `$$...$$` block can be used labelled with the following syntax:

	$$
	LaTeX
	$$ (label_name)

or a MyST maths block can labelled, with this syntax:

	```{math}
	:label: label_name
	LaTeX
	```

In both cases, the equations can be referenced using `{eq}`label_name`.

Here are two examples:

$$
\sin^2(x)+\cos^2(x)\equiv 1
$$ (trig_id1)

```{math}
:label: trig_id2
\sin(2x) = 2\sin(x)\cos(x) 
```

The equations can then be referenced: {eq}`trig_id1` and {eq}`trig_id2`.

```{note}
The usual LaTex `\label` command will not work in a Jupyter Book.
```

## Macros

User defined *macros* can be added into the `_config.yml` file. They should be defined in this position:

	sphinx:
	  mathjax3_config:
        tex:
	        macros:

The syntax is a little awkward and not discussed further here, but as examples, `_config.yml` contains common latex macros with Mathjax comptatible versions: 

- `\bm`

For example, 

$$\bm{\epsilon}=\mathbf{e}_z$$ 

## MathJax extensions

[MathJax extensions](https://docs.mathjax.org/en/latest/input/tex/extensions/index.html) can be in loaded by editing the config, e.g.

	sphinx:
	  mathjax3_config:
        tex:
          packages: "[+]": ["mathtools", "physics", "color"]
        loader:
          load: ["[tex]/mathtools", "[tex]/physics", "[tex]/color"]

For example, 

```{math}
z=\frac{\splitfrac{ab+cd+ef+gh+ij}{+kl+mn+op+qr}}{y}
```

```{math}
T=\sum_{
    \mathclap{\substack{i_1,\ldots,i_n=1 \\ j_1,\ldots,j_m=1}}}^d
    T_{j_1,\ldots,j_m}^{i_1,\ldots,i_n}
    E_{i_1,\ldots,i_n}^{j_1,\ldots,j_m}
```

```{math}
\order{x^2}
```

```{math}
\color{red}{x} + \color{blue}{y}
```
