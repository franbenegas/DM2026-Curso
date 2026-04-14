---
title: Clase No2 - ODEs y NODEs
---

# ODEs y NODEs

**Fecha:** 13/04/2026

:::{iframe} https://www.youtube.com/embed/kgRSMKC8Rrg
:width: 100%
:::

## Ecuaciones diferenciales ordinarias (ODEs)

Un ejemplo de como escribir una ecuacion:

$$
\frac{du}{dt} = f(u, t, \theta), \quad u(t_0) = u_0
$$

donde $u(t) \in \mathbb{R}^n$ es el estado del sistema, ... .

:::{note} Ecuaciones diferenciales con derivadas de mayor orden
...
:::

:::{note} Ecuaciones diferenciales en derivadas parciales
...
:::

### Ejemplos


## Inferencia estadística

% Modelo para el estado, modelo para el ruido
% Errores gaussianos
% Ajuste de trayectorias (trajectory matching)

### Ejemplo (continuado)

% Como se ve esto en el caso del sistema Lotka-Volterra?


## Ecuaciones diferenciales ordinarias neuronales (NODEs)

Las NODEs fueron introducidas por {cite}`chen2018neural` ...

## Ejemplo (implementación computacional)

En Myst, podemos incluir codigo!

```julia
using DifferentialEquations
using Plots
```