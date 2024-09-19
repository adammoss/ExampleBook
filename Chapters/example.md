# Radioactivity Example

## Units

Before we begin, a quick note on units:

1. Nuclear sizes are typically of order $10^{-15} \, {\rm m}$ (1 fm).
2. Nuclear time scales have a vast range, e.g. half-life can range from $10^{-20} \, {\rm s}$ to greater than the age of the Universe!

*Working in these units will make calculations easier and will be less likely to lead to mistakes.*

## Radioactive decay

The nucleus consists of protons (positively charged) and neutrons (neutral), which have approximately the same mass (the mass difference is important however in calculations!).

````{admonition} Radioactive Decay
:class: definition
The spontaneous emission of radiation(s) that changes the state of the nucleus.
````

````{admonition} Nuclear notation
:class: definition
We will define a nucleus by

```{math}
:label: eq-nuclear_notation
^A_Z {\rm X}
```

where $Z$ is the proton number (also called the atomic number) and $A=Z+N$ is the mass number, where $N$ is the number of neutrons. $X$ is the name of the nucleus, and is unique for a given $Z$. The $Z$ number is therefore sometimes omitted for common nuclei.
````

- Alpha decay ($\alpha$): A helium nucleus (2 protons and 2 neutrons) is emitted from a parent nucleus.
- Beta decay ($\beta$): A high energy electron or positron (the anti-particle of an electron) is emitted from the nucleus.
- Gamma decay ($\gamma$): The nucleus de-excites and emits a gamma ray photon (like electron transitions leading to photons in atoms). It is very energetic, interacts weakly with matter, and is uncharged.

```{figure} plots/stability.png
:width: 60%
:name: fig-stability
:alt: A chart showing the relationship between the number of neutrons (N) and the number of protons (Z) in stable and unstable nuclides. The "valley of stability" is highlighted, with dots representing stable nuclides. Regions outside the valley indicate where unstable nuclides lie, which are prone to radioactive decay such as alpha or beta emission, shown by directional arrows at the edges of the valley. The line N=Z signifies equal numbers of protons and neutrons.
Segre chart.
```

We will discuss each of these in more detail shortly. Of about 2500 known nuclides, only about 300 are stable.  The stable nuclei form a narrow distribution on a plot of $N$ versus $Z$, as shown in [](fig-stability).

## Natural radioactivity

The earth formed about $4.5 \times 10^9$ years ago from the debris of long dead stars.

:::{table} The disintegration series of the heavy elements ($n$ is an integer).
:widths: auto
:align: center
| Name of Series | Type | Final Nucleus (Stable) | Nucleus | Half-Life (year) |
| --- | --- | --- | --- | --- |
| Thorium | 4n | $^{208}$Pb | $^{232}$Th | $1.41\times10^{10}$ |
| Neptunium | 4n+1 | $^{209}$Bi | $^{237}$Np | $2.14\times10^{6}$ |
| Uranium | 4n+2 | $^{206}$Pb | $^{238}$U | $4.47\times10^{9}$ |
| Actinium | 4n+3 | $^{207}$Pb | $^{235}$U | $7.04\times10^{8}$ |
:::

If it were not for the very long half-life of $^{235}$U and $^{238}$U there would be no natural uranium and so no obvious source of nuclear power.

## Radioactive Decay Law

The number of radioactive nuclei, $dN$, decaying in a time $dt$ is proportional to $N$, so

```{math}
:label: eqn:decay1
\frac{dN}{dt} = - \lambda N
```

where $\lambda$ is the disintegration or decay constant, which has units of inverse time. [](eqn:decay1) can be integrated to give the exponential law of radioactive decay

```{math}
:label: eqn:decay2
N= N_0 e^{-\lambda t}
```

where $N_0$ is the number of nuclei at $t = 0$.  The half-life, $t_{1/2}$, is the time taken for half of the material to decay.  Putting $N = N_0/2$ in [](eqn:decay2) gives

```{math}
:label: eqn:decay3
\frac{N_0}{2} = N_0 e^{-\lambda t_{1/2}}
```

```{math}
:label: eqn:decay4
t_{1/2} = \frac{\ln 2}{\lambda}
```

### Example

````{exercise} 
:label: exercise-carbon-dating 
Question:
Primary cosmic radiation converts $^{14}$N in the atmosphere into $^{14}$C,  which has a half-life of 5730 years.  This combines with oxygen to form ${\rm CO}_2$ which is taken up by plants.  When the plant dies the decay of the $^{14}$C   radioactivity can be used to determine its age.

If the activity of a sample of wood found in the tomb of one of the Pharaohs is 6.8 counts/minute/gram of carbon and the activity of $^{14}$C in living plant material is 15.3 counts/min/gram of carbon, what is the age of the wood sample?
````

````{solution} exercise-carbon-dating 
:class: dropdown 
Solution:
```{math}
:label: eqn-carbon-dating 
\begin{align*}
N&= N_0 e^{-\lambda t}\,, \\ 
t&= \frac{\ln(N_0/N)}{\lambda}\,, \\ 
t&= t_{1/2} \frac{\ln(N_0/N)}{\ln 2}\,, \\ 
t&= 6704 \, {\rm years}\,.
\end{align*}
```
````


### Decay sequences

As discussed, nuclei often decay in sequence. Consider the decay sequence of 3 nuclei:

```{math}
:label: eq-decay
A\,{\xrightarrow {\lambda _{A}}}\,B\,{\xrightarrow {\lambda _{B}}}\,C
```

where nuclide $A$ is the first in the chain, and nuclide $C$ is stable. The notation means nuclide $A$ will decay with decay constant $\lambda_A$, and nuclide $B$ will decay with decay constant $\lambda_B$. The differential equations describing the system are

```{math}
:label: eq-diff1
\frac{dN_A}{dt} = - \lambda_{A} \, N_A\,,
```

```{math}
:label: eq-diff2
\frac{d N_B}{dt} = \lambda_{A} \, N_A - \lambda_{B} \, N_B\,,
```

```{math}
:label: eq-diff3
\frac{d N_C}{dt} = \lambda_{B} \, N_B\,.
```

````{admonition} Be Careful
:class: caution
We will primarily be interested in nuclear masses. If you are given atomic masses (denoted by a subscript A) you can convert to nuclear mass by

```{math}
:label: eq-mass
M_N = M_A - Z m_{\rm e}\,,
```

where $m_{\rm e}$ is the electron mass. I will emphasise this point several times as it's an easy thing to slip up on!
````
