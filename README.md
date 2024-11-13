-Instrucciones para usar el "Modelos_de_Clustering_(Agrupación).ipynb"

Paso 1: Al cargar el archivo Asegúrate de modificar la ruta (data) para que coincida con la ubicación correcta en tu sistema antes de ejecutar el análisis.

Por ejemplo, en el script donde se realiza el análisis, actualiza la variable data de la siguiente manera: data = pd.read_csv('D:\\UNAD_ANDRES\\Mall_Customers.csv')


1. Análisis Exploratorio de Datos (AED)

En esta etapa inicial, hemos identificado la distribución de tres variables clave:
•	Edad: Esto nos permite entender la segmentación de clientes según sus edades.
•	Ingreso Anual y Puntaje de Gasto: Estas variables nos ayudan a evaluar el poder adquisitivo y el comportamiento de gasto de los clientes.
Además, analizamos la matriz de correlación, que muestra las relaciones entre las variables y facilita la selección de las más significativas para el análisis de clustering.

2. Selección del Número Óptimo de Clusters
Para determinar el número óptimo de clusters, evaluamos tres métricas principales:
•	Método del Codo (Inercia): Esta métrica mide cuánta variación es explicada por cada cluster adicional. Observamos un "codo" alrededor de 4 clusters, lo cual sugiere que, a partir de ahí, los beneficios de agregar más clusters disminuyen.
•	Coeficiente de Silhouette: Con este índice evaluamos la cohesión dentro de cada cluster y la separación entre ellos  y valores cercanos a 1 indican que los clusters están bien definidos.
•	Índice Calinski-Harabasz: Este índice mide la densidad y separación de los clusters, y nuestros resultados también sugieren que 4 clusters es una elección adecuada.
Basados en estos análisis, hemos consensuado que el número óptimo de clusters es 4.

3. Interpretación de los Clusters
Con K-means y k=4, los clusters resultantes, representados en la gráfica de dispersión del ingreso anual frente al puntaje de gasto, revelan patrones claros. Cada color representa un cluster con comportamientos específicos de ingreso y gasto. podemos inferir los siguientes segmentos:

•	Cluster 1: Clientes con alto ingreso y alto gasto. Probablemente se sientan atraídos por productos premium y tienen un alto poder adquisitivo.
•	Cluster 2: Clientes con bajo ingreso y bajo gasto. Buscan productos accesibles y gestionan de forma cuidadosa su gasto.
•	Cluster 3: Clientes con alto ingreso pero bajo gasto. Este grupo podría incluir personas ahorradoras o selectivas en sus compras.
•	Cluster 4: Clientes con bajo ingreso pero alto gasto. Este grupo puede incluir aquellos que priorizan ciertas compras importantes.

4. Evaluación Final del Modelo
Utilizamos la puntuación de Silhouette y el Índice Calinski-Harabasz para validar la calidad de los clusters. Una puntuación de Silhouette cercana a 0.5 o superior indica una buena separación entre los clusters y una agrupación efectiva de los clientes.

Conclusión
Estos clusters representan perfiles de clientes bien definidos, lo cual brinda una base sólida para diseñar estrategias de marketing personalizadas o programas de fidelización específicos. Los resultados indican que el modelo ha captado adecuadamente los patrones de comportamiento en cuanto a ingresos y gastos, permitiéndonos dirigir mejor las acciones comerciales y fortalecer el impacto de nuestras iniciativas.
