# S5----MEGALINE
¿Qué tarifa de prepago le genera más ingresos al operador de telecomunicaciones?
Prueba de hipotesis.

## Descripción
Se determina qué tarifa de prepago (Surf o Ultimate) genera más ingresos para  el operador de telecomunicaciones Megaline, para que el departamento comercial pueda ajustar el presupuesto de publicidad.

Se ponen a prueba las siguientes dos hipótesis:
* El ingreso promedio de los usuarios de las tarifas Ultimate y Surf difiere.
* El ingreso promedio de los usuarios en el área de estados Nueva York-Nueva Jersey es diferente al de los usuarios de otras regiones.

## Herramientas utilizadas
![Python](https://img.shields.io/badge/:Python-024A86?style=for-the-badge&logo=python&logoColor=white&labelColor=101010)</br>
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Seaborn](https://img.shields.io/badge/seaborn-%233F4F75.svg?style=for-the-badge&logo=seaborn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white)

## Conclusiones
* "Son diferentes los ingresos promedio procedentes de los usuarios de los planes de llamada Ultimate y Surf."
* "El ingreso promedio de los usuarios del área NY-NJ es diferente al de los usuarios de otras regiones."
  
## Profundización técnica
* Lectura, exploración - df.sample(#): muestra aleaotria.
*  Preparación de datos - tipos de datos: df[col].astype('int/str/float/bool'), valores auscentes, duplicados, nombres de columnas.
* * Redondeo de enteros (duración de llamada) - mt.ceil(var)
  * Tipo de datos datetime - pd.to_datetime(df[col],format='%Y-%m-%d:%H-%M-%S') , df['col_date'].dt.month
  * Enriquecer los datos - Agregar columnas si es necesario para facilitar cálculos.
* Manejo de dataframes: 
* *  Uso de tablas pivote - df.pivot_table( index='',column='', value='', aggfunc='')
  *   Fusión de tablas - df1.merge(df2, on='col', how='inner/outer/left/right')
  *   Eliminación columnas de tables - df.drop('col', axis='columns')
  *   Ciclos For y bloques condicionales if-elif-else
  *   Filtrado de df - df[df['col']== value]
  *   Extracción de segmentos de df - df.loc[rows,cols] : rangos, listas o todo(:)
  *   Concatenación df - pd.concat([s1,s2], axis='columns')
* Visualización: 
* * Graficos de dos datasets - cols=['s1','s2'], df.plot(y=cols,kind='bar/scatter/pie', title='',xlabel='',ylabel='',figsize=''), plt.legend['..','...'], plt.show()
  * Histogramas - df[col].plot(bins= #, kind='hist', title='',xlabel='',ylabel='',figsize='')
  * Diagramas  caja-bigotes para revision de media, max, min, outliers/valores atípicos - sns.boxplot(df['col']), plt.show()
* Calculos:
* * Media - s.mean()
  * varianza - np.var(s)
* Pruebas de hipótesis:
* * Plantear hipótesis nula (=) y alternativa (!=)
  * Identificar si se hace sobre 2 poblaciones o sobre población-valor
  * Aplicación de Taylor test -  st.ttest(s1,s2, equal_var=False/True)
  * Identificar si es de 1 o 2 colas
  * Elegir valor alfa de acuerdo a la precisión ( 10%, 5%, 0.5%)
  * Rechazar o aceptar hipótesis -  para 2 colas, if (results.pvalue < alpha): "Rechazamos hipótesis nula"
