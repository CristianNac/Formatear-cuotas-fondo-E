# Formateo de valores fondo E AFP Hábitat

## Extracción de información

La información del fondo E de la AFP hábitat se extrajo desde la página de la superintendencia de pensiones en formato csv, 
la cual contiene información del fondo E de las distintas AFP desde el año 2000, a continuación se adjunta el link de la 
[Superintendencia de pensiones](https://www.spensiones.cl/apps/valoresCuotaFondo/vcfAFP.php). 

## Proceso de carga de la información en Python

Para cargar la información se utilizó la librería Pandas de Python mediante el siguiente código: ```python  
pd.read_csv('vcfA2002-2024.csv', skiprows = startrow -1, nrows = num_rows) ```
Se debieron añadir los argumentos skiprows y nrows para considerar las filas en blanco que existían en el csv.



