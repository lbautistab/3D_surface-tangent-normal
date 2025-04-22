# Visualización 3D de una Superficie con su Plano Tangente y Recta Normal

Este repositorio contiene un script en Python que visualiza en 3D la superficie de la función $\ f(x, y) = x^2 + y^2 \$, junto con su plano tangente y la recta normal en el punto $(1, 1, 2)$.

## 📌 Descripción

La función considerada es una superficie parabólica:

$\ f(x, y) = x^2 + y^2\$

El script genera:
- La **superficie** de la función.
- El **plano tangente** en el punto (1, 1, 2).
- La **recta normal** en el mismo punto, con dirección dada por el vector **(2, 2, -1)**.

Todo esto se visualiza mediante un gráfico 3D usando `matplotlib`.

## 📁 Estructura del código

- **Definición de la función** `f(x, y)`.
- **Malla de puntos** para graficar la superficie.
- **Cálculo del plano tangente** en el punto dado.
- **Cálculo de la recta normal**.
- **Visualización 3D** combinando superficie, plano y recta.

## 🧰 Requisitos

Asegúrate de tener instaladas las siguientes librerías:

```bash
pip install numpy matplotlib

