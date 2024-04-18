# Formateo de valores fondo E AFP Hábitat

## Extracción de información

La información del fondo E de la AFP hábitat se extrajo desde la página de la superintendencia de pensiones en formato csv, 
la cual contiene información del fondo E de las distintas AFP desde el año 2000, a continuación se adjunta el link de la 
[Superintendencia de pensiones](https://www.spensiones.cl/apps/valoresCuotaFondo/vcfAFP.php). 

## Proceso de carga de la información en Python

Para cargar la información se utilizó la librería Pandas de Python mediante el siguiente código: ```python  
pd.read_csv('vcfA2002-2024.csv', skiprows = startrow -1, nrows = num_rows) ```
Se debieron añadir los argumentos skiprows y nrows para considerar las filas en blanco que existían en el csv.

## Preprocesamiento de la información

La información que se necesita para realizar el análisis es la que se encuentra en la columna fecha y la que se encuentra en la
bajo la columna de valor cuota de la AFP Hábitat. Para eliminar el resto de la información mediante la librería pandas,
se seleccionaron las columnas que debían eliminarse y se cambió el nombre de la columna de valor cuota de Hábitat por Cuota.

## Transformación de los datos

Luego de limpiar la información se agregan cuatro columnas de nombres: Open, High, Low, Close; que hacen referencia al valor
valor inicial en un día, el valor mayor que obtiene durante el día, al más bajo y al valor con que cierra en el mercado respectivamente.

## Exportar la información a formato csv

Finalmente, la información es exportada a formato csv utilizando el método de pandas: ``` valor_cuota.to_csv('Habitat-E.csv', index = False, sep = ',') ```


