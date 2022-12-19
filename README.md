# Análisis de la evolución del Bitcoin

En este proyecto final he realizado un análisis de múltiples dimensiones del precio del Bitcoin. A partir de un par de fuentes de datos he querido aplicar todo lo aprendido, además de descubrir nuevas herramientas y nuevas potencialidades. 

## ETL: Extraer, transformar y cargar
Al solo encontrar bases de datos algo desfasadas o con ausencia de datos útiles, he utilizado la herramienta Selenium para descargar la base de datos de los precios del BTC de una página web. Me es muy útil ya que a cada vez que se reinicia el kernel obtenemos datos completamente actualizados. Por otro lado, la base de datos de Twitter es descargada de Kaggle en formato csv. Realizo una limpieza de datos exhaustiva y conformo los dataframe según los objetivos.

## Estadística descriptiva
En esta sección realizo visualizaciones clave de la evolución de distintos parámetros del BTC; desde una perspectiva financiera se puede apreciar como hubo un auge en el 2020 pero actualmente parece que están retornando los precios, el volumen y la capitalización del mercado a estándares de hace 5 años. Hay una caída muy marcada, además de una inestabilidad en los precios.

## Análisis de sentimientos en Twitter; correlación con el Bitcoin
Traemos de nuevo la base de datos de Twitter previamente limpiada y la ajustamos a las exigencias técnicas de la herramienta de análisis VADER. Esta herramienta nos da una puntuación según expresiones clave que van desde el -1 (muy negativo) al 1 (muy positivo) por cada tweet; añadimos estas columnas al dataframe y realizamos un sumatorio; de esta forma tendremos la carga "emotiva" por día. Luego establecemos un score por cada tweet, evidentemente no todo tweet pesa igual ya que hay multitud de factores como la virabilidad, las interacciones, los seguidores, etc. que afectan directamente. Correlacionamos con la evolución de los precios y extraemos correlaciones. 

## Modelos de machine learning; análisis predicitivo del valor del Bitcoin
En este apartado he querido aplicar modelos predictivos, pese a que arriba comprobamos que el valor es muy inestable. Probamos primero con ARIMA, cuyos resultados me decepcionan pero no me desaniman. Pasamos al algoritmo XGBoost, basado en un mejoramiento de los clásicos algoritmos de árboles de decisiones. Tras el procesamiento del dataframe para que se adapte a las exigencias del algoritmo obtenemos una predicción que se ajusta bastante a la evolución del precio real; de tal modo que decido extraer una predicción a 10 días. 

## Next Steps
En este apartado hay representados un conato de estudio acerca de la correlación del consumo energético, la minería y los precios del BTC. Debido a la escasez de fuentes de datos gratuitas lo dejo, por el momento, para el futuro. 

PD: Debido al peso de la base de datos de Twitter, Github no me permite hacerla accesible en la carpeta de data. Se puede descargar de aquí: https://www.kaggle.com/datasets/gautamchettiar/bitcoin-sentiment-analysis-twitter-data
