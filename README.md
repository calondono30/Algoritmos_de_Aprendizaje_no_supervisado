-Instrucciones para usar el "Modelos_de_Clustering_(Agrupación).ipynb"

Paso 1: Al cargar el archivo Asegúrate de modificar la ruta (data) para que coincida con la ubicación correcta en tu sistema antes de ejecutar el análisis.

Por ejemplo, en el script donde se realiza el análisis, actualiza la variable data de la siguiente manera: data = pd.read_csv('D:\\UNAD_ANDRES\\Mall_Customers.csv')


Análisis Exploratorio y Visualización de Datos

1. Distribución de la Edad, Ingreso Anual y Puntaje de Gasto: Al principio, se crearon histogramas para ver la distribución de tres variables clave:

•	Edad: Este gráfico nos permite observar cómo se distribuyen las edades de los clientes.
•	Ingreso Anual: Muestra cómo varía el ingreso anual de los clientes. Nos ayuda a entender si la mayoría de ellos tiene ingresos similares o si hay gran diversidad.
•	Puntaje de Gasto: Este puntaje refleja el nivel de gasto de los clientes y su variación. Es útil para identificar si hay grupos con diferentes comportamientos de gasto.

Estas visualizaciones nos ayudan a identificar patrones, como grupos de edad predominantes o rangos de ingresos y gastos similares, lo cual será útil para la segmentación.

2. Matriz de Correlación: Se utilizó un gráfico de calor para mostrar la correlación entre variables numéricas. En este caso, cada celda de la matriz representa el nivel de correlación entre dos variables:

Si el "Ingreso Anual" tiene una fuerte correlación con el "Puntaje de Gasto", esto podría indicar que las personas con mayores ingresos tienden a gastar más.

 La matriz de correlación ayuda a identificar relaciones directas o inversas entre las características, que pueden guiar el análisis de clustering.

Preprocesamiento de los Datos
3. Codificación y Normalización:
•	Codificación de Género: Se convierte la variable de género en valores numéricos para facilitar su uso en el modelo de clustering. En este caso, 0 puede representar un género y 1 el otro.

•	Normalización: Se escalan los datos de todas las variables seleccionadas para que tengan media 0 y desviación estándar 1. Esto es fundamental porque los algoritmos de clustering, como K-means, son sensibles a la escala de los datos.

Estos pasos aseguran que cada variable contribuya de manera justa en el análisis y que el modelo no se vea sesgado por diferencias de escala.

Determinación del Número Óptimo de Clusters

4. Cálculo de Métricas para Distintos Números de Clusters:

•	Inercia: Representa la suma de las distancias cuadradas entre cada punto y el centroide del grupo al que pertenece. Cuando disminuye notablemente, indica que el número de clusters es adecuado (Método del Codo).

•	Coeficiente de Silhouette: Mide la cohesión y separación de los clusters; valores altos indican que los clusters están bien definidos y separados.

•	Índice Calinski-Harabasz: Compara la separación entre clusters con la cohesión dentro de cada cluster; valores más altos sugieren clusters mejor definidos.

A partir de los gráficos (Inercia, Coeficiente de Silhouette e Índice Calinski-Harabasz), se puede elegir el número óptimo de clusters (en este caso, basado en el valor máximo de Silhouette).

Entrenamiento Final con K-means y Visualización de los Clusters
 
 5. Entrenamiento con el Número Óptimo de Clusters: Se entrena el modelo K-means usando el número de clusters determinado previamente. Luego, se asigna un grupo (o "cluster") a cada cliente en los datos.

       6. Visualización de los Clusters: Se crea un gráfico de dispersión que muestra los clusters formados, utilizando el Ingreso Anual y el Puntaje de Gasto como ejes, y los colores representan diferentes grupos de clientes.

Esta visualización nos permite observar si los clusters hacen sentido visualmente. podemos ver grupos de clientes que ganan y gastan más, o aquellos que ganan menos, pero tienen un gasto moderado o alto. Esto ayuda a identificar perfiles de clientes.


Análisis Jerárquico y Dendrograma

7. Dendrograma para Agrupación Jerárquica: Se emplea un dendrograma para visualizar cómo se agruparían los clientes en una jerarquía. En un dendrograma, los puntos más cercanos indican grupos con mayor similitud entre sí.

El dendrograma puede revelar relaciones interesantes que un análisis plano de clustering no muestra. Por ejemplo, puede evidenciar subgrupos dentro de clusters grandes o cómo se relacionan los clusters entre sí.

Evaluación Final del Modelo

8. Resumen de Resultados:
•	Número óptimo de clusters: Se elige el número de clusters que maximiza el Coeficiente de Silhouette, proporcionando la segmentación más significativa.
•	Coeficiente de Silhouette y Calinski-Harabasz: Estos valores finales confirman la cohesión y separación efectiva de los clusters. Un Coeficiente de Silhouette cercano a 1 sugiere una muy buena separación, mientras que un Índice Calinski-Harabasz alto indica que los clusters están claramente definidos.

Esta evaluación final permite validar que el número óptimo de clusters segmenta bien a los clientes, logrando perfiles bien diferenciados. Esto es útil para estrategias comerciales personalizadas o decisiones de negocio, como campañas de marketing dirigidas a diferentes segmentos de clientes.

Este análisis identifica patrones y relaciones en los datos de clientes, divide a los clientes en grupos claramente definidos y proporciona una representación visual de estos grupos. Las empresas pueden usar esta segmentación para adaptar sus estrategias a cada tipo de cliente, aumentando la efectividad en áreas como marketing, ventas y retención de clientes.
