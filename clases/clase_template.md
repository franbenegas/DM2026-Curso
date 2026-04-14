---
title: Plantilla de Clase - MyST Markdown
---

# Título de la Clase

**Fecha:** DD/MM/YYYY

% Esto es un comentario en MyST (no aparece en el output)

:::{seealso} Documentación de MyST
Esta plantilla está basada en la sintaxis de [MyST Markdown](https://myst-parser.readthedocs.io/en/v0.15.0/index.html). Consultá la documentación oficial para más detalles y opciones avanzadas.
:::

---

## Video de la clase

:::{iframe} https://www.youtube.com/embed/VIDEO_ID
:width: 100%
:::

---

## Texto y formato básico

Párrafo normal con **negrita**, *cursiva*, y `código inline`.

Lista sin orden:
- Elemento uno
- Elemento dos
  - Sub-elemento
  - Sub-elemento

Lista numerada:
1. Primer paso
2. Segundo paso
3. Tercer paso

Tabla:

| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| a         | b         | c         |
| x         | y         | z         |

---

## Matemática

Ecuación inline: el estado $u(t) \in \mathbb{R}^n$ evoluciona en el tiempo.

Ecuación en bloque:

$$
\frac{du}{dt} = f(u, t, \theta), \quad u(t_0) = u_0
$$

Ecuación numerada con etiqueta:

$$
\mathcal{L}(\theta) = \sum_{i=1}^{N} \| u(t_i; \theta) - y_i \|^2
$$ (eq:loss)

Referencia a la ecuación: ver {eq}`eq:loss`.

Sistema de ecuaciones (entorno `align`):

$$
\begin{align}
\frac{dx}{dt} &= \alpha x - \beta x y \\
\frac{dy}{dt} &= \delta x y - \gamma y
\end{align}
$$

---

## Código

### Julia

```julia
using DifferentialEquations
using Plots

# Definir el sistema de Lotka-Volterra
function lotka_volterra!(du, u, p, t)
    α, β, γ, δ = p
    du[1] = α * u[1] - β * u[1] * u[2]
    du[2] = δ * u[1] * u[2] - γ * u[2]
end

# Condición inicial y parámetros
u0 = [1.0, 0.5]
p  = [1.5, 1.0, 3.0, 1.0]
tspan = (0.0, 10.0)

prob = ODEProblem(lotka_volterra!, u0, tspan, p)
sol  = solve(prob, Tsit5())
plot(sol)
```

### Python

```python
import numpy as np
from scipy.integrate import solve_ivp
import matplotlib.pyplot as plt

def lotka_volterra(t, u, alpha, beta, gamma, delta):
    x, y = u
    return [alpha*x - beta*x*y, delta*x*y - gamma*y]

sol = solve_ivp(lotka_volterra, [0, 10], [1.0, 0.5], args=(1.5, 1.0, 3.0, 1.0))
plt.plot(sol.t, sol.y.T)
plt.show()
```

---

## Admonitions (banners)

:::{note}
Esto es una nota genérica. Útil para aclaraciones o información adicional.
:::

:::{tip}
Esto es un tip o consejo práctico para el estudiante.
:::

:::{warning}
Esto es una advertencia. Útil para señalar errores comunes o cuidados especiales.
:::

:::{danger}
Esto es un peligro. Para conceptos que pueden llevar a errores graves.
:::

:::{important}
Esto resalta algo importante que no debe pasarse por alto.
:::

:::{seealso}
Para referencias cruzadas: ver también la Clase 1 y {cite}`rackauckas2020universal`.
:::

Admonition con título personalizado:

:::{note} Caso especial: EDOs autónomas
Cuando $f$ no depende explícitamente de $t$, la ecuación se llama **autónoma**:

$$
\frac{du}{dt} = f(u, \theta)
$$

Los puntos de equilibrio satisfacen $f(u^*, \theta) = 0$.
:::

:::{dropdown} Demostración (hacer clic para expandir)
Esta es una sección colapsable, útil para demostraciones largas o material optativo.

$$
\frac{d}{dt}\|u\|^2 = 2 \langle u, f(u) \rangle
$$
:::

---

## Figuras e imágenes

```{figure} ../images/dm.png
:width: 300px
:align: center
:name: fig-ejemplo

Epígrafe de la figura. Se puede referenciar como {numref}`fig-ejemplo`.
```

---

## Referencias y citas

Cita de un artículo: {cite}`chen2018neural`.

Cita de múltiples artículos: {cite}`chen2018neural,rackauckas2020universal`.

Al final de la página MyST renderiza la bibliografía automáticamente con:

```
:::{bibliography}
:::
```

:::{bibliography}
:::
