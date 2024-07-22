pip install matplotlib

import matplotlib.pyplot as plt
import numpy as np

# Función para dibujar el receptáculo basado en la secuencia de Fibonacci
def receptaculo_fibonacci(n_points, scale):
    r = np.sqrt(np.arange(n_points)) * scale
    theta = np.pi * (1 + np.sqrt(5)) * np.arange(n_points)
    x = r * np.cos(theta)
    y = r * np.sin(theta)
    return x, y

# Función para dibujar un pétalo geométrico
def dibujar_petalo(ax, center, angle, width, height):
    # Coordenadas del pétalo (elipse)
    t = np.linspace(0, 2 * np.pi, 100)
    petal_x = width * np.cos(t)
    petal_y = height * np.sin(t)
    
    # Rotación y traslación del pétalo
    R = np.array([[np.cos(np.radians(angle)), -np.sin(np.radians(angle))],
                  [np.sin(np.radians(angle)), np.cos(np.radians(angle))]])
    petal = np.dot(R, np.array([petal_x, petal_y]))
    petal[0] += center[0]
    petal[1] += center[1]
    ax.fill(petal[0], petal[1], color='yellow', edgecolor='orange')

# Crear la figura y los ejes
fig, ax = plt.subplots(figsize=(10, 10))
ax.set_aspect('equal')

# Dibujar el receptáculo con la secuencia de Fibonacci
n_points = 300
scale = 0.2  # Ajuste de escala para centrar el receptáculo dentro de los pétalos
x, y = receptaculo_fibonacci(n_points, scale)
ax.scatter(x, y, color='brown', s=10, zorder=5)

# Dibujar los pétalos geométricos
num_petalos = 20
width = 2  # Ancho del pétalo
height = 8  # Alto del pétalo
for i in range(num_petalos):
    angle = i * (360 / num_petalos)
    dibujar_petalo(ax, center=(0, 0), angle=angle, width=width, height=height)

# Configuración de la gráfica
ax.set_xlim(-15, 15)
ax.set_ylim(-15, 15)
ax.axis('off')  # Ocultar los ejes

plt.show()
