# Promedio-Ponderado-con-Filtros-Digitales
El objetivo es generar métodos númericos a traves de codigos en python colab para compartirlos y evitar el robo de softwares.

Primer codigo en Python/Colab para hacer calculo de promedio ponderado con Filtros Digitales

# def weighted_average(values, weights):
  """
  Calcula el promedio ponderado de una lista de valores y pesos.

  Args:
    values: Una lista de valores numéricos.
    weights: Una lista de pesos numéricos, del mismo tamaño que values.

  Returns:
    El promedio ponderado de los valores.
  """
  if len(values) != len(weights):
    raise ValueError("La longitud de las listas de valores y pesos debe ser la misma.")

  if any(w < 0 for w in weights):
      raise ValueError("Los pesos no pueden ser negativos.")

  weighted_sum = sum(v * w for v, w in zip(values, weights))
  sum_of_weights = sum(weights)

  if sum_of_weights == 0:
        return 0  # Manejar el caso donde la suma de pesos es cero

  return weighted_sum / sum_of_weights

  # Calculo de cierto promedio ponderado
valores = [10, 20, 30, 40, 50]
pesos = [1, 2, 1, 2, 1]

try:
  promedio = weighted_average(valores, pesos)
  print(f"El promedio ponderado es: {promedio}")
except ValueError as e:
  print(f"Error: {e}")
