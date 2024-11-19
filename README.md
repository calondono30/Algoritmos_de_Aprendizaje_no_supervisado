-Instrucciones para usar el "Modelos_de_Clustering_(Agrupación).ipynb"

Paso 1: Al cargar el archivo Asegúrate de modificar la ruta (data) para que coincida con la ubicación correcta en tu sistema antes de ejecutar el análisis.

Por ejemplo, en el script donde se realiza el análisis, actualiza la variable data de la siguiente manera: df = pd.read_csv('D:\\UNAD_ANDRES\\Mall_Customers.csv')


Interpretación y Análisis de Resultados.
1. Análisis Exploratorio de los Datos (EDA)

•	Distribución de Edad:
La mayoría de los clientes tienen entre 20 y 40 años, con un pico en los 30 años, lo que sugiere que el centro comercial atrae principalmente a clientes jóvenes y de mediana edad.
•	Distribución de Ingresos Anuales:
Los ingresos anuales están distribuidos uniformemente entre $15,000 USD y $137,000 USD con una ligera concentración entre $50,000 USD y $75,000 USD, lo cual indica una clientela predominantemente de clase media.
•	Distribución de Puntuación de Gastos:
La puntuación de gastos varía ampliamente entre 1 y 100, con una distribución relativamente uniforme. Esto refleja una diversidad en los hábitos de gasto, desde clientes muy conservadores hasta aquellos más propensos a gastar.

2. Preprocesamiento de los Datos
•	Codificación de Género:
La variable Gender fue codificada como 0 para hombres y 1 para mujeres, permitiendo su inclusión como variable numérica en los modelos de clustering.
•	Estandarización:
Las características numéricas (Age, Annual Income, y Spending Score) fueron escaladas para tener una media de 0 y una desviación estándar de 1. Esto es crucial porque los algoritmos de clustering son sensibles a las escalas de las variables  y el escalado asegura que todas las características contribuyan por igual al modelo.

3. Selección de Características
Se utilizaron las características Age, Annual Income (k$) y Spending Score (1-100), ya que son relevantes para segmentar a los clientes según su edad, capacidad de gasto y comportamiento de consumo.

4. Entrenamiento del Modelo
•	K-means Clustering:
Se seleccionaron 5 clusters basados en el método del codo. Este número representa el punto donde la disminución del WCSS (suma de distancias dentro del cluster) deja de ser significativa, equilibrando simplicidad y precisión en la segmentación.
El gráfico del método del codo muestra un cambio significativo en la pendiente cuando se pasa de 4 a 5 clusters, lo que indica que k=5 es un número óptimo. Después de este punto, la mejora en WCSS es marginal y no justifica un aumento en la complejidad del modelo.
•	Hierarchical Clustering:
Se utilizó el método de Ward, que minimiza la varianza dentro de los clusters, proporcionando agrupamientos jerárquicos que permiten observar las relaciones entre los clientes.

5. Evaluación del Desempeño del Modelo
K-means Clustering:
•	Coeficiente de Silhouette: 0.416
Esto indica una estructura razonable de los clusters, con una buena separación entre ellos.
•	Índice de Calinski-Harabasz: 125.100
Refleja una buena densidad y separación de los clusters.
Hierarchical Clustering:
•	Coeficiente de Silhouette: 0.390
Ligeramente inferior al de K-means, lo que sugiere una menor cohesión dentro de los clusters.
•	Índice de Calinski-Harabasz: 107.826
También inferior al de K-means, indicando una menor separación entre clusters.

6. Visualización de Resultados
•	K-means Clustering:
Los clusters formados muestran una buena separación en el espacio de características, agrupando a los clientes según su ingreso anual y puntuación de gasto. Esto permite identificar segmentos clave, como clientes de alto ingreso y alta propensión a gastar.
•	Dendrograma de Hierarchical Clustering:
El dendrograma ilustra cómo los clientes se agrupan jerárquicamente en diferentes niveles de distancia. Esto proporciona una visión estructural útil para comprender las relaciones entre los datos.
•	Resultados de Hierarchical Clustering:
Aunque los clusters jerárquicos presentan una separación aceptable, la cohesión dentro de los clusters es ligeramente inferior en comparación con K-means.

7. Documentación de Resultados
•	K-means Clustering:
Este método es eficiente y ofrece una mejor separación y cohesión de los clusters. Es particularmente adecuado para conjuntos de datos grandes y permite una interpretación directa de los resultados.
•	Hierarchical Clustering:
Proporciona una perspectiva jerárquica útil para entender las relaciones entre clientes, pero puede ser menos eficiente y menos cohesivo con conjuntos de datos más grandes.

Conclusión
Ambos métodos proporcionan una segmentación útil de los clientes del centro comercial:
•	K-means Clustering ofrece mejor cohesión y separación de los clusters, siendo ideal para segmentar grupos con características distintas.
•	Hierarchical Clustering complementa al ofrecer una visión jerárquica que permite explorar relaciones más profundas entre los clientes.
La elección del método depende del contexto del análisis y los objetivos específicos. Para aplicaciones prácticas, como estrategias de marketing, K-means puede ser preferible debido a su eficiencia y claridad en los resultados.
