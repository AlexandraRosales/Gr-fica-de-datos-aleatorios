# Gr-fica-de-datos-aleatorios
Programa en Python que simula una máquina de Galton de 3000 canicas y 12 niveles

#Importa la biblioteca Numpy y le asigna el alias np. 
import numpy as np
#Importa la biblioteca Matplotlib y se le asigna el alias plt que sirve para graficar.
import matplotlib.pyplot as plt

#Definimos la función  que toma como parámetros n_canicas(número de canicas) y n_niveles(número de niveles de obstáculos).
def simular(n_canicas, n_niveles):
    

    #Creamos un array de tamaño n_canicas lleno de ceros de tipo entero qeu almacena el número de veces que cada canica cae a la derecha.
    resultados = np.zeros(n_canicas, dtype=int)
    
    #Iniciamos un bucle de repetición por cada canica.
    for i in range(n_canicas):
    #Iniciamos otro bucle que se repite por cada nivel. 
        for _ in range(n_niveles):
    #Genera un número aleatorio entre 0 y 1, si el número es menor a 0.5 incrementa el contador de caídas a la derecha para esa canica.
            if np.random.rand() < 0.5:
    #Incremneta en uno al conteo de caídas a la derecha para la canica i.
                resultados[i] += 1
    #Devuelve el array "resultados" que contiene el número de caídas a la derecha para cada canica.            
    return resultados

#Definimos la función "graficar_histograma" que toma como parámetros resltado y n_niveles. 
def graficar_histograma(resultados, n_niveles):
    """
    Grafica un histograma de los resultados de la máquina de Galton.
    
    Parámetros:
    resultados (np.array): Resultados de las caídas de las canicas.
    n_niveles (int): Número de niveles de obstáculos.
    """
    #Crea el histograma de los resultados. El parámetro bins=n_niveles+1 asegura que haya un contenedor adicional para cubrir todas las posibles caídas y edgecolor="black" agrega bordes negros a las barras del histograma.
    plt.hist(resultados, bins=n_niveles+1, edgecolor='black')
    #Añade título al histograma.
    plt.title("Simulación de la Máquina de Galton")
    #Se agrega como etiqueta para el eje x.
    plt.xlabel("Número de caídas a la derecha")
    #Se agrega como etiqueta para el eje y.
    plt.ylabel("Cantidad de canicas")
    #Muestra la gráfica en pantalla.
    plt.show()

#Definimos el número de canicas para la simulación.
n_canicas = 3000
#Definimos el número de niveles de obstáculos.
n_niveles = 12

#Llamamos a la función _simular con los parámetros del número de camicas y número de niveles y guarda los resultados en la variable resultados.
resultados = simular(n_canicas, n_niveles)

#Llamamos a la función para graficar el histograma de los resutados obtenidos.
graficar_histograma(resultados, n_niveles)


Reflexión: El bootcamp hasta ahora me ha dejado grandes enseñanzas con los retos y tareas de cada módulo y al seguir adelante con los desafíos que estaán por venir, pues, con practica y paciencia podemos obtener mejores resultados.
