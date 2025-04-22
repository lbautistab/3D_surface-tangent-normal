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
```
## 📝 Código en Python

```bash
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# Definir la función f(x, y) = x^2 + y^2
def f(x, y):
    return x**2 + y**2

# Crear una malla de puntos para la superficie
gx, gy = np.meshgrid(np.linspace(-2, 2, 100), np.linspace(-2, 2, 100))
gz = f(gy, gx)

# Punto de interés donde se calcula la normal y el plano tangente
x0, y0, z0 = 1, 1, 2

# Dirección del vector normal al plano tangente
normal_dir = np.array([2, 2, -1])

# Parámetro t para graficar la recta normal
t = np.linspace(-2, 2, 20)
line_x = x0 + normal_dir[0] * t
line_y = y0 + normal_dir[1] * t
line_z = z0 + normal_dir[2] * t

# Definición del plano tangente en torno al punto (1,1)
px, py = np.meshgrid(np.linspace(0, 2, 10), np.linspace(0, 2, 10))
pz = z0 + 2 * (px - x0) + 2 * (py - y0)

# Crear la figura 3D
fig = plt.figure(figsize=(16, 12))
ax = fig.add_subplot(111, projection='3d')

# Graficar la superficie
ax.plot_surface(gy, gx, gz, cmap='viridis', alpha=0.6)

# Graficar la recta normal
ax.plot(line_x, line_y, line_z, color='red', linewidth=2, label='Normal')
ax.scatter(x0, y0, z0, color='black', s=50, label='Punto (1,1,2)')

# Graficar el plano tangente
ax.plot_surface(px, py, pz, color='cyan', alpha=0.5)

# Etiquetas de los ejes
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Z')

# Mostrar leyenda
ax.legend()

# Mostrar el gráfico
plt.show()

```
## 🎯 Resultado

![Superficie3D](https://github.com/user-attachments/assets/50c875d2-1910-4652-846a-12d8ca0b7e9a)


