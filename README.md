## 1. Título del proyecto

Fashion Boutique Data Sales 2024-2025📊.

## 2. Descripción proyecto

Este proyecto consiste en la realización de un análisis exploratorio de datos (EDA) a partir de un conjunto de datos sintéticos del sector retail de la moda, que representa el ciclo completo de ventas de una fashion boutique multimarca durante un período comprendido entre agosto de 2024 y agosto de 2025. El objetivo principal es identificar patrones y tendencias en el comportamiento de compra de los clientes y reflejar los resultados en un dashboard interactivo.

El contexto de análisis se sitúa en una tienda que trabaja con múltiples marcas y categorías de productos. A partir de la información disponible en el dataset, se busca resolver problemas como la identificación de productos y marcas con mejor desempeño, las causas de devolución, la evolución de las ventas según temporada, entre otros.

Para llevar a cabo el desarrollo del proyecto se aplicaron técnicas de limpieza y transformación de datos, seguidas de un análisis descriptivo, y finalmente la construcción de  un dashboard que integra los resultados obtenidos y permite una visualización clara de los principales indicadores clave.

## 3. Pasos del proyecto

* Se localizó y descargó la base de datos en formato .csv desde Kaggle para su procesamiento en Excel.
* Al importar el archivo, la información aparecía agrupada en una sola columna. Se utilizó la herramienta Texto en columnas, seleccionando la coma como delimitador para separar correctamente los datos.
* Una vez organizadas las columnas, se aplicó un formato de Tabla a todo el conjunto de datos para facilitar su gestión y se personalizó el diseño.
* En una nueva hoja (Hoja1), se empleó la función =CONTARA (debido a que los datos no son números, sino códigos) para determinar el volumen total de ventas registradas.
* Se añadió la columna “Duplicados” en la base de datos principal. Utilizando la función =SI(SI.ERROR(BUSCARV, se verificó la existencia de códigos repetidos.
* Mediante la función =SUMA en la Hoja1, se comprobaron la cantidad de duplicados detectados. Al obtener un resultado de 0, se confirmó que no era necesario eliminar ninguna fila.
* Para identicar datos nulos o faltantes, se utilizó la función =CONTAR.BLANCO en los encabezados. Se detectaron datos faltantes en las columnas de Talla, Valoración del cliente y Razón de devolución.
* En la columna “Talla”, se identificó que los vacíos correspondían a productos sin talla (accesorios) o a datos desconocidos. Se creó una columna auxiliar con la función =SI para asignar las etiquetas “Accesorio” o “Desconocido”, ocultando posteriormente la columna original.
* Para la columna “Customer rating”, se sustituyeron los espacios vacíos por “No valorado” con la función =SI.
* En la columna “Return reason”, se aplicó la función =SI para marcar como “No return” aquellos campos vacíos, debido a que la ausencia de motivo implica estrictamente que el producto no fue devuelto.
* Se ajustó el formato de las columnas numéricas. Para ello, se utilizó el comando Ctrl+L para reemplazar los puntos por comas y permitir que Excel reconociera los valores numéricos correctamente.
* Para evitar errores en el formato porcentaje (donde valores como 35,4 se convertían en 3540%), se creó una columna nueva que dividía los valores originales entre 100, aplicando después el formato porcentaje.
* Se creó la columna “Cantidad_Descuento” para calcular el valor dejado de ganar en cada venta, restando el precio actual (“Current_price”) al precio original (“Original_price”).
* Para analizar tendencias, se crearon las columnas “Día_Compra” y “Mes_Compra”. Se combinaron las funciones =NOMPROPIO y =TEXTO (con formatos “dddd” y “mmmm”) para obtener los nombres de los días y meses con la primera letra en mayúscula.
* En la columna “Stock_quantity”, se aplicó un Formato Condicional con una escala de colores: verde para stock suficiente (más de 10 unidades), amarillo para stock crítico (1-9 unidades) y rojo para agotado.
* Se añadió una columna de estado del stock utilizando la función =SI para clasificar los productos como “OK”, “Pocas unidades” o “Agotado”, facilitando la detección de problemas de reposición.
* Para simplificar el recuento de devoluciones, se creó la columna “Devuelto_Número”, transformando mediante la función =SI los valores “True” en 1 y “False” en 0.
* Se generó la columna “Ingreso_marca” utilizando la función =SI. Esta columna asigna un valor de 0 si el producto fue devuelto y el precio de venta si no lo fue, reflejando así la ganancia real de la empresa.
* Se creó una nueva hoja (tablas_dinámicas) para generar las Tablas Dinámicas necesarias para el estudio de los datos.
* A partir de las tablas dinámicas, se insertaron diversos Gráficos Dinámicos (barras, circulares y de puntos) para representar la información.
* Se personalizaron los colores y estilos de los gráficos, seleccionando los más relevantes para la presentación final.
* Se duplicó la hoja de “tablas_dinámicas” para configurar la grabación de las macros del proyecto.
* Se diseñó una hoja nueva (Dashboard) donde se organizó, en primer lugar, el diseño, los KPI’s y las tablas o gráficos dinámicos estáticos.
* Se configuraron las macros específicas para alternar la visualización entre cantidad de ingresos y volumen de ventas en los gráficos seleccionados.
* Se insertaron Segmentadores de datos por Marca, Color, Estación y Categoría para permitir una exploración personalizada de la información.
* Se realizaron ajustes estéticos finales para asegurar la limpieza y funcionalidad del Dashboard. 

## 4. Estructura del proyecto
#### Excel (fashion_boutique): Base de datos original.
#### Excel (Fashion_boutique_macros_habilitados):
- BBDD_fashion_boutique (Datos sintéticos procesados, filtrados y limpiados)
- Hoja1 (Hoja para identificar volumen de registros, eliminación de duplicados y tratamiento de datos nulos o faltantes)
- Tablas_dinámicas (Tablas dinámicas para la exploración de tendencias)
- Tablas_dinámicas (2) (Copia de las tablas dinámicas para la grabación de macros)
- Dashboard (Dashboard Fashion Boutique)
#### README.md (Descripción del proyecto)



## 5. Instalación y requisitos

Para que el Dashboard funcione correctamente:

#### Requisitos
* Tener instalado Microsoft Excel.
* Descargar el archivo con extensión .xlsm (habilitado para macros)
#### Pasos para la ejecución

Como el proyecto incluye Macros, se deben seguir los siguientes pasos:
* Antes de abrir el archivo, haz clic derecho sobre el archivo y selecciona propiedades. Abajo del todo, marca la casilla “Desbloquear” y dale a aceptar. (Si no se hace esto, Windows bloquea las macros debido a la introducción de malware).
* Abre el Excel y pulsa “Habilitar contenido”.
* Ve a la pestaña de Dashboard y usa los segmentadores y los macros para ver los datos que te interesen.

## 6. Resultados y Conclusiones

* La tienda registró un total de 2176 ventas, generando unos ingresos de 159.502,63€ El ticket promedio por cliente se sitúa en 73,30€
* Zara es la marca líder tanto en volumen de ventas (313 unidades) como en generación de ingresos (22.737,40€), cuyo artículo más vendido es Bottoms, sin embargo, el que aporta un mayor número de ingresos es el Outerwear.
* La marca más inconsistente es Gap, con el menor número de ventas e ingresos.
* La categoría de Accesorios es la más popular en volumen (402 ventas) pero las prendas Outerwear son las que más ingresos generan (41.141,43€) debido a su mayor precio por unidad.
* El color Green lidera las ventas (222), seguido de cerca por el Red y el Black
* Se observa un mayor número de ventas (575) e ingresos (40.127,69€) en Summer, mientras que el Winter representa el periodo de menor actividad.
* El 14,71% de los productos vendidos son devueltos, principalmente por motivos como “Changed Mind” (68 casos) o “Size Issue” (60 casos).
* La valoración media general es aceptable, destacando Uniqlo con la mejor puntuación (3,11) y Mango con la más baja (2,78).
* La marca que mayor cantidad de ingresos pierde por realizar descuentos es Mango, seguido de Banana Republic y Zara. En esta última se entiende la pérdida debido a que es la que tiene un mayor número de ventas.
* La marca que más devoluciones sufre es Ann Taylor, con 51 unidades devueltas. Sabiendo que esta marca vendió 257 artículos, prácticamente ⅕ de las ventas son devueltas al almacén. La razón principal es “Changed Mind”, un factor subjetivo difícil de controlar. No obstante, resulta esencial centrar la atención en las siguientes razones: fallo en el color, en el artículo, en la talla y en los problemas de calidad.

#### Hallazgo crítico: Error en la base de datos original.
* Durante el análisis de las tablas dinámicas por fechas, se localizó una anomalía grave en el origen de los datos:
* Inconsistencia Fecha-Estación: Se detectaron ventas con fecha de agosto marcadas como “Winter”.
* Distribución anómala: Una sola fecha acumula más de 1600 ventas (06/08/2025), mientras que el resto de los registros se repartían en los restantes 600 datos.
* Conclusión: Se determinó que la columna “Purchase_Date” es errónea de origen, mientras que la columna “Season” es coherente y homogénea. Por ello, el análisis de tendencias se ha basado en la estacionalidad y no en la fecha de compra.
#### Conclusiones:
* Este análisis es útil para los responsables de la tienda en los siguientes aspectos:
* Optimizar el inventario: dado que las ventas caen en Winter y suben en Summer, deben planificar la reposición de stock con antelación.
* Estrategia de tallas: el alto volumen de devolución por “Size Issue” sugiere que sería recomendable que revisen las guías de tallas en la web o el etiquetado de las prendas para reducir costes logísticos.
* Focalización en Marketing: Aunque los Accesorios se venden mucho, el esfuerzo en publicidad debería centrarse en Outerwear y Shoes, ya que tienen un impacto mucho mayor en el margen por ingresos netos.
* Control de Descuentos: El gráfico de “Cantidad Descontada por Marca” muestra que Mango es la marca donde más margen se pierde por rebajas. Se debería evaluar si estos descuentos son necesarios para mantener su volumen de ventas o si se pueden reducir.
* Valoración de Mango: A pesar de ser una de las marcas que más vende, es la peor valorada por los clientes. Se recomienda investigar si la calidad percibida o la falta de precisión en las tallas está dañando la imagen de la marca, ya que vender mucho no siempre garantiza la rentabilidad a largo plazo si el cliente no queda satisfecho.

## 7. Próximos pasos

* Realizar una comparativa interanual: Una vez obtenidos datos de 2026, crear un dashboard comparativo para medir el crecimiento o decrecimiento respecto al período actual.

* Geolocalización de ventas online: si se añaden datos de ciudades, integrar un mapa en el dashboard para ver dónde tiene más éxito cada marca.

* Corrección del origen de datos temporales: Contactar con los proveedores de datos o el departamento técnico para subsanar la anomalía en la columna Purchase_Date, asegurando que las fechas futuras sigan una distribución lógica y coherente con las estaciones.


## 8. Contribuciones

Este proyecto fue desarrollado con fines académicos. Aunque se encuentra finalizado, se aceptan sugerencias o mejoras técnicas.

## 9. Autores y agradecimientos.

Lucía García Martínez - [@luciagarciamartinez]
##### Agradecimientos:
A ThePower Education, por proporcionarme las herramientas y el conocimiento técnico necesarios para llevar a cabo este análisis.



