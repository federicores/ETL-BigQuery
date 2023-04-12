Architecture:
   The Architecture of this project can be discussed as below:
   
   <img src="https://github.com/SreekarJammula/ETL-BigQuery/blob/master/Assets/arch(2).png">

Cloud Storage: Almacenamiento en la nube de datos estructurados y no estructurados. Para el desarrollo del proyecto se usó este servicio para subir los archivos planos como.
<img src="https://github.com/SreekarJammula/ETL-BigQuery/blob/master/Assets/Screenshot%20(3).png">

BigQuery: Es el repositorio donde se crean las tablas y se sincroniza con la información previamente almacenada en archivo planos para darle una estructura y un sentido a la solución. Cuando los datos ya están cargados se puede explorar la información a través del Lenguaje de Consulta Estructurado SQL.
El programador de consultas puede activar las secuencias de comandos de python que solicitarán a BigQuery que realice las consultas y luego el resultado se puede almacenar en Google Cloud Storage.
Consulta de datos: se hace con la API de Python para que BigQuery desarrolle scripts de Python. La misma API se pude usar para exportar los resultados a los depósitos de GCS como archivos csv. El objetivo principal de elegir la API de python es porque proporciona algunas funciones poderosas que facilitan la codificación y también nos permite escribir una consulta persistente que se puede cambiar fácilmente. 
Consulta.py: Para encontrar el perfil del cargo más relevante para la necesidad puntual de nuestro cliente. Esta consulta está diseñada de tal manera que devuelve la cantidad de perfiles que se consideran como los mas idoneos para el cargo solicitado. 

Consulta.py El script toma dos parámetros, la tabla de entrada) y el nombre del archivo de salida en el depósito de almacenamiento de Google como se indica. Un uso más avanzado puede ser el uso de comodines para las tablas, como "gsod20*", de modo que se puedan analizar los datos de la década. Siempre se recomienda dar a los cubos de GCS nombres adecuados al exportar los datos. Internamente, la secuencia de comandos consulta la tabla de entrada y almacena los resultados en una tabla creada previamente en Google BigQuery (que se denomina dest_table_id en la secuencia de comandos). Luego llama a una función para escribir esta tabla en el almacenamiento de Google.

Google Colab en la nube permite desarrollar aplicaciones analíticas mediante el lenguaje de Python. Es de uso gratuito y ya tiene muchas librerías instaladas. Para el desarrollo del proyecto es muy útil, por la facilidad de conexión con BigQuery para la implementación de los modelos de aprendizaje automático seleccionados [28].
DataStudio: Es una herramienta de visualización de datos de Google, su objetivo es permitir el análisis de datos de forma fácil y sencilla para visualizar resultados de forma inmediata. Para el desarrollo del proyecto se creó varios tableros de control para ver los resultados como se observa en la Figura.

Programación del procesamiento de consultas:
BigQuery no tiene una disposición para programar las consultas para que se ejecuten automáticamente. Esto se puede hacer usando paquetes de terceros como CRON o AIRFLOW. Además, se pueden utilizar las funciones de Google Cloud recientemente introducidas o GOOGLE APPSCRIPT, que es una API de JavaScript desarrollada por Google.

El principal desafío es familiarizarse con la API de Python. Crear tablas dinámicamente usando la API es un poco difícil. Esto me llevó a crear manualmente tablas para almacenar los resultados de la consulta. Además, no se puede validar la consulta antes de ejecutarla como sea posible en la interfaz de usuario web. Esto puede ser muy útil en el caso de consultas complejas que procesan grandes cantidades de datos.

Este proyecto me ha permitido comprender mejor Google BigQuery y cómo ayuda a resolver problemas de análisis de datos a gran escala. BigQuery usa un formato de almacenamiento en columnas y escala automáticamente. Por lo tanto, al escribir consultas eficientes que limitan el número de columnas a las que se accede, los resultados se generan en segundos. Teniendo en cuenta la arquitectura sin servidor, se puede decir que el precio es muy razonable. Al cliente se le cobra por almacenar los datos y por la cantidad de datos procesados.
