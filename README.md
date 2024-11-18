-Instrucciones para usar el "Modelos_de_Clustering_(Agrupación).ipynb"

Paso 1: Al cargar el archivo Asegúrate de modificar la ruta (data) para que coincida con la ubicación correcta en tu sistema antes de ejecutar el análisis.

Por ejemplo, en el script donde se realiza el análisis, actualiza la variable data de la siguiente manera: df = pd.read_csv('D:\\UNAD_ANDRES\\Mall_Customers.csv')


Interpretación y Análisis de Resultados

1. Análisis Exploratorio de los Datos (EDA)
•	Distribución de Edad: La mayoría de los clientes tienen entre 20 y 40 años, con un pico notable en los 30 años. Esto sugiere que el centro comercial atrae principalmente a una clientela joven y de mediana edad.
•	Distribución de Ingresos Anuales: Los ingresos anuales de los clientes están distribuidos uniformemente entre $15,000 USD y $137,000 USD, con una ligera concentración alrededor de $50,000 USD a $75,000 USD.
•	Distribución de Puntuación de Gastos: La puntuación de gastos varía ampliamente entre 1 y 100, con una distribución relativamente uniforme. Esto indica una diversidad en los hábitos de gasto de los clientes.

2. Preprocesamiento de los Datos
•	Codificación de Género: La variable Gender fue codificada como 0 para hombres y 1 para mujeres, permitiendo su uso en modelos de machine learning.
•	Estandarización: Las características numéricas fueron escaladas para tener una media de 0 y una desviación estándar de 1, lo cual es crucial para algoritmos de clustering que son sensibles a las escalas de las variables.

3. Selección de Características
•	Se utilizaron todas las características (Age, Annual Income (k$), Spending Score (1-100)) para el entrenamiento de los modelos de clustering, ya que todas son relevantes para segmentar a los clientes.

4. Entrenamiento del Modelo
•	K-means Clustering: Se seleccionaron 5 clusters basados en la estructura de los datos y la interpretación de los resultados.
•	Hierarchical Clustering: Se utilizó el método de Ward para minimizar la varianza dentro de cada cluster.

5. Evaluación del Desempeño del Modelo
K-means Clustering:
•	Coeficiente de Silhouette: 0.408, lo que indica una estructura de cluster razonable con una buena separación entre los clusters.
•	Índice de Calinski-Harabasz: 123.42, sugiriendo una buena densidad y separación de los clusters.

Hierarchical Clustering:
•	Coeficiente de Silhouette: 0.390, ligeramente inferior al de K-means, indicando una menor cohesión dentro de los clusters.
•	Índice de Calinski-Harabasz: 107.83, también inferior al de K-means, sugiriendo una menor separación entre los clusters.

6. Visualización de Resultados
•	K-means Clustering: Resultados de K-means Clustering Los clusters formados muestran una buena separación en el espacio de características, con clientes agrupados según sus ingresos anuales y puntuación de gastos.
•	Dendrograma de Hierarchical Clustering: !Dendrograma de Hierarchical Clustering El dendrograma muestra la jerarquía de los clusters y cómo se agrupan los clientes a diferentes niveles de distancia.
•	Resultados de Hierarchical Clustering: !Resultados de Hierarchical Clustering Los clusters jerárquicos también muestran una buena separación, aunque con una cohesión ligeramente inferior en comparación con K-means.

Documentación de Resultados
•	K-means Clustering: Este método es eficiente y proporciona una buena separación de los clusters. Es adecuado para grandes conjuntos de datos y permite una fácil interpretación de los resultados.
•	Hierarchical Clustering: Este método es útil para entender la estructura jerárquica de los datos y es más interpretativo, aunque puede ser menos eficiente para grandes conjuntos de datos.

Conclusión
Ambos métodos de clustering proporcionan una segmentación útil de los clientes del centro comercial. K-means ofrece una mejor cohesión y separación de los clusters, mientras que el clustering jerárquico proporciona una visión jerárquica de las relaciones entre los clientes. La elección del método depende del contexto y de los objetivos específicos del análisis.


