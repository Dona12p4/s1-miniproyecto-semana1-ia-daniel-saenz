# Bitacora de uso de IA

Esta bitacora tambien fue organizada con apoyo de IA generativa a partir de la conversacion sostenida en el chat. La IA se uso principalmente como herramienta de orientacion, explicacion y verificacion de criterios, no como sustituto del desarrollo del taller. El estudiante supervisa esta bitacora para verificar que se registren los usos pertinentes y que el contenido refleje de forma honesta el papel de la IA en el trabajo.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** recibir orientacion general para entender el dataset `datos_celda_industrial_sinteticos.csv` y saber que aspectos debian revisarse antes de formular una tarea de IA.

**Situacion consultada:** el estudiante indico que el dataset tenia muchas variables y pidio ayuda para entender como abordarlo sin perderse en los datos.

**Apoyo recibido:** la IA explico una forma ordenada de mirar el dataset: identificar cantidad de registros, variables disponibles, tipos de columnas, posible variable objetivo, problemas de calidad, riesgos de fuga de informacion y utilidad para una primera linea base.

**Aprendizaje aplicado:** se entendio que no era necesario pedirle a la IA que resolviera directamente el analisis, sino usar codigo de pandas para obtener evidencia: primeras filas, tipos de datos, resumen numerico, faltantes, duplicados y distribucion de categorias. La IA sirvio como guia para interpretar que significaban esas salidas.

**Alcance de esta entrada:** esta entrada registra apoyo conceptual para leer el dataset y orientar el analisis. Las respuestas finales del notebook quedan bajo revision del estudiante.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** diagnosticar un error de ejecucion en el notebook de la clase Semana 1, Dia 3, relacionado con la preparacion del entorno.

**Situacion consultada:** al ejecutar una celda de importacion de librerias, aparecio el error `ModuleNotFoundError: No module named 'sklearn'` en la linea `from sklearn.datasets import load_iris, load_wine, load_diabetes`.

**Apoyo recibido:** la IA explico que el problema no era la sintaxis del codigo, sino que el entorno de Python/Jupyter no tenia instalada la libreria `scikit-learn`, que se importa como `sklearn`.

**Criterio aclarado:** se explico que `%pip install scikit-learn` podia servir para el notebook de clase que usa datasets de `scikit-learn`, pero que para la exploracion inicial del miniproyecto no era necesario instalar ni importar `scikit-learn`, porque se estaba trabajando con un CSV cargado con `pandas`.

**Alcance de esta entrada:** se registro una orientacion tecnica sobre dependencias del entorno. La instalacion o ejecucion de paquetes queda bajo control del estudiante.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** aclarar la diferencia entre el codigo de ejemplo de la clase S1_D3 y el codigo necesario para el miniproyecto.

**Situacion consultada:** el estudiante noto que aparecian datos del dataset Iris, con columnas como `sepal length`, `petal length`, `target` y `species`, cuando se suponia que estaba trabajando con el dataset industrial.

**Apoyo recibido:** la IA explico que el codigo de la clase tenia una parte de preparacion del entorno y otra parte que cargaba Iris como ejemplo pedagogico. Se aclaro que para el miniproyecto se debia trabajar con el DataFrame `df` cargado desde `pd.read_csv(DATA_PATH)`, no con `iris_clean`.

**Aprendizaje aplicado:** se distinguio que algunas importaciones generales, como `numpy`, `pandas`, `matplotlib`, `display` y configuraciones de pandas, pueden servir como preparacion. En cambio, las lineas especificas de Iris, como `load_iris`, `iris_clean`, `species` o `source = "sklearn_iris"`, pertenecen al ejemplo de clase y no al dataset del proyecto.

**Alcance de esta entrada:** se registro una explicacion para evitar mezclar datasets y para entender que partes del codigo de clase se pueden adaptar.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** entender que revisa cada celda de exploracion inicial y como usarla para diagnosticar la calidad del dataset.

**Situacion consultada:** el estudiante necesitaba usar funciones vistas en clase como `head()`, `info()`, `describe()`, `isna()`, `duplicated()` y `value_counts()`, pero queria entender que significaba cada salida y como aplicarla al CSV industrial.

**Apoyo recibido:** la IA explico para que sirve cada funcion: `head()` para ver primeras filas, `info()` para tipos y valores no nulos, `describe()` para rangos y resumen numerico, `isna()` para faltantes, `duplicated()` para duplicados y `value_counts()` para distribuciones categoricas.

**Aprendizaje aplicado:** se entendio que estas celdas permiten obtener evidencia directamente desde el notebook. La IA se uso para comprender el proposito de los comandos y no para reemplazar la inspeccion que el estudiante hizo con pandas.

**Alcance de esta entrada:** se registra apoyo para entender y adaptar codigo de exploracion inicial visto en clase. La IA no modifico el notebook original.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** comprender como interpretar los resultados del diagnostico de calidad y como convertirlos en hallazgos tecnicos.

**Situacion consultada:** el estudiante tenia salidas del notebook sobre primeras filas, tipos de datos, resumen numerico, faltantes, duplicados y distribucion de `estado_operativo`, pero necesitaba entender como leerlas para completar la tabla de diagnostico.

**Apoyo recibido:** la IA explico como relacionar cada salida con un aspecto de calidad: faltantes, duplicados, tipos de datos, categorias inconsistentes, valores fuera de rango, posibles outliers, posible fuga de informacion y desbalance de clases.

**Criterio aclarado:** se explico que la accion recomendada antes de modelar no significa borrar todo automaticamente, sino documentar una decision tecnica: revisar origen de faltantes, validar duplicados, normalizar categorias, analizar valores extremos, excluir variables con posible fuga de informacion y no depender solo de accuracy cuando hay desbalance.

**Alcance de esta entrada:** se registra apoyo de interpretacion y criterio tecnico. La tabla final debe ser revisada por el estudiante contra las salidas reales del notebook.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** recibir orientacion sobre visualizaciones utiles para interpretar el dataset.

**Situacion consultada:** el estudiante no estaba seguro de cuales graficos servian para la seccion de visualizacion e interpretacion, ni como decidir si una grafica aportaba a una decision tecnica.

**Apoyo recibido:** la IA explico que las visualizaciones debian servir para formular hipotesis o detectar problemas, no para decorar. Se converso sobre graficos utiles como barras de `estado_operativo`, boxplot de `vibracion_mm_s` por estado y dispersion entre variables numericas como temperatura, consumo y carga.

**Aprendizaje aplicado:** se entendio que una visualizacion debe responder una pregunta: por ejemplo, si las clases estan desbalanceadas, si una variable cambia segun el estado operativo o si hay puntos extremos que requieren revision.

**Alcance de esta entrada:** se registra apoyo para elegir e interpretar graficas. La ejecucion, revision de salidas y conclusiones finales quedan bajo responsabilidad del estudiante.

## 2026-06-14

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** aclarar como formular una tarea principal de IA para el punto 5 del miniproyecto.

**Situacion consultada:** el estudiante queria entender como decidir entre clasificacion, regresion, deteccion de anomalias o agrupamiento, sin intentar resolver todas las posibilidades del dataset.

**Apoyo recibido:** la IA explico que el tipo de tarea depende de la salida esperada. Si se quiere predecir una categoria como `estado_operativo`, la formulacion corresponde a clasificacion. Si se quisiera estimar un numero como `consumo_kWh`, seria regresion; si no hay etiquetas, podria pensarse en agrupamiento o anomalias.

**Criterio aclarado:** se converso sobre la diferencia entre variables de entrada candidatas y variables que conviene excluir. Se explico que identificadores como `registro_id` no son buenas entradas predictivas y que columnas posteriores al turno, como `diagnostico_post_turno` o `parada_reportada_post_turno`, pueden causar fuga de informacion si se usan para predecir `estado_operativo`.

**Alcance de esta entrada:** se registra apoyo conceptual para tomar la decision del tipo de tarea y justificarla. La seleccion final y la redaccion del punto 5 quedan bajo revision del estudiante.

## 2026-06-15

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** construir el comentario critico del punto 6 sobre linea base y metrica inicial.

**Situacion consultada:** el estudiante ya tenia una propuesta de linea base con `DummyClassifier`, clase mayoritaria `normal`, `accuracy`, matriz de confusion, `balanced accuracy` y `recall` por clase. Luego pidio contexto para explicar por que una metrica alta podia ser enganosa en este caso.

**Apoyo recibido:** la IA respondio preguntas sucesivas del estudiante sobre que pasaria si el modelo predice siempre `normal`, por que eso podria producir una `accuracy` alta, por que esa lectura seria incompleta en un dataset desbalanceado y por que la clase `falla` requiere revisarse con metricas adicionales. Tambien ayudo a ordenar la idea de que una matriz de confusion, el `recall` de la clase `falla` y la `balanced accuracy` permiten evaluar mejor si el modelo realmente detecta estados operativos relevantes.

**Aprendizaje aplicado:** se entendio que una metrica global alta no siempre significa que el modelo sea util. En este caso, si la clase `normal` domina el dataset, un modelo podria acertar muchos registros sin detectar adecuadamente las fallas. Por eso, la linea base funciona como comparacion minima y el comentario critico debe explicar el riesgo de depender solo de `accuracy`.

**Alcance de esta entrada:** se registra apoyo para redactar y justificar el comentario critico del punto 6. La decision final sobre la metrica, la interpretacion y la redaccion entregada quedan bajo revision del estudiante.

## 2026-06-15

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** revisar la reproducibilidad del notebook y aclarar la evidencia de organizacion de archivos para el punto 8.

**Situacion consultada:** el estudiante pregunto si el notebook funcionaria para el profesor aunque la carpeta no estuviera en el Escritorio del computador del estudiante, sino en otra ubicacion como Descargas. Tambien pidio aclaracion sobre que significa incluir un enlace al repositorio o una evidencia de organizacion de archivos.

**Apoyo recibido:** la IA explico que una ruta absoluta como `C:\Users\USER\OneDrive\Escritorio\...` puede fallar en otro computador, porque depende del usuario y de la ubicacion exacta de la carpeta. Se recomendo usar rutas relativas dentro del proyecto, manteniendo el CSV en `data/` y el notebook en `notebooks/`, para que el archivo pueda ejecutarse desde la raiz del proyecto o desde la carpeta del notebook.

**Cambio aplicado:** se ajusto la celda de carga del dataset para buscar `datos_celda_industrial_sinteticos.csv` mediante rutas relativas: `data/datos_celda_industrial_sinteticos.csv` o `../data/datos_celda_industrial_sinteticos.csv`. Asi, si el profesor descarga la carpeta completa en Descargas, Escritorio u otra ruta, el notebook no depende de la ruta local del estudiante. Tambien se completo `README.txt` para explicar la estructura de entrega, la ubicacion del dataset, la forma recomendada de ejecutar el notebook y la diferencia entre entregar un enlace de GitHub o una carpeta organizada.

**Criterio aclarado:** se entendio que el enlace al repositorio se refiere a una URL de GitHub si el docente solicita publicar o compartir el proyecto por GitHub. Si no se usa GitHub, la evidencia de organizacion de archivos puede ser la carpeta de entrega con una estructura clara, por ejemplo `data/`, `notebooks/`, `docs/` y `README.txt`.

**Verificacion realizada:** se valido que el notebook siguiera siendo un archivo JSON valido y que la ruta relativa encontrara el CSV tanto desde la raiz del proyecto como desde la carpeta `notebooks/`.

**Alcance de esta entrada:** se registra apoyo tecnico y conceptual sobre reproducibilidad. La decision final sobre entregar enlace de GitHub o carpeta organizada depende de lo solicitado por el docente.

## 2026-06-15

**Herramienta usada:** Codex / ChatGPT.

**Objetivo:** verificar y completar el checklist minimo de reproducibilidad del punto 8.

**Situacion consultada:** el estudiante pidio revisar solamente el checklist del punto 8, sin modificar otras partes del notebook.

**Apoyo recibido:** la IA verifico que el notebook fuera un archivo valido, que se ejecutara de arriba hacia abajo, que el dataset estuviera adjunto en `data/`, que las respuestas y visualizaciones estuvieran relacionadas con el dataset, que existiera la bitacora de uso de IA y que hubiera evidencia de organizacion mediante `README.txt` y la estructura de carpetas.

**Cambio aplicado:** se marcaron como completados los siete elementos del checklist del punto 8. No se lleno la tabla de bitacora dentro del notebook ni se modificaron otras respuestas.

**Verificacion realizada:** se valido el notebook como JSON y se ejecuto con `nbconvert` antes de completar los checks.

**Alcance de esta entrada:** se registra el apoyo puntual para verificar y completar el checklist. Las demas secciones del notebook quedaron fuera del alcance de esta interaccion.
