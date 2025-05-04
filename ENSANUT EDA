def separador():
    print("\n" + "=" * 170 + "\n")
def header(Titulo):
  por=((170-len(Titulo))//10)
  a=int(1.2*por)
  print("."*a+"·"*a+"~"*a+"≈"*a+"≋"
  *int(por*.2),Titulo,"≋"*int(por*.2)
  +"≈"*a+"~"*a+"·"*a+"."*a,"\n\n")
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import matplotlib.gridspec as gridspec
import math

df = pd.read_csv("ENSANUT_final_ingles.csv")


header('COLUMNS AND ROWS')
df=df.astype('int64')
print(f'Database consists of {df.shape[0]} rows and {df.shape[1]} columns\n')
print(df.head())
print(df.info())

header('NAMES AND DATA TYPES')
tipos=pd.DataFrame({'Tipo':df.dtypes})
tipos.reset_index(inplace=True)
tipos.columns=['Column name', 'Type']
print(tipos)
plt.figure(figsize=(8,8))
color=sns.color_palette('pastel')
df.dtypes.value_counts().plot(kind='pie', autopct='%1.1f%%', colors=color,startangle=90)
plt.title('Type of Data', size=16)
plt.ylabel('') #para que no salga etiqueta en el eje y
plt.show()


header('DATAFRAME DESCRIPTION')
print(df.describe(include='all'))
dfnum=df.select_dtypes(include=[np.number])
plt.figure(figsize=(12,18))
dfscal=(dfnum-dfnum.mean())/dfnum.std()
sns.boxplot(data=dfscal, orient='h', palette='viridis')
plt.title('NUMERIC VARIABLES DISTRIBUTION')
plt.tight_layout()
plt.show()


header('NORMALIZATION OF COLUMN NAMES')
df.columns = df.columns.str.lower()
print(f'New names\n: {df.columns.to_list}')

header('DATA TYPE CORRECTION')
verificar=True #pequeño bucle para verificar que todos los datos quedaran en float o int
for i in df.columns:
  if not pd.api.types.is_numeric_dtype(df[i]):
    verificar=False
    break
if verificar:
  print('\nALL COLUMNS ARE NUMERIC ✓\n\n')
else:
  print('NOT ALL COLUMNS ARE NUMERIC X')

header('DATA VERIFICATION')
verificar=True
for i in df.columns:
  if not pd.api.types.is_categorical_dtype(df[i]):
    verificar=False
    break
if verificar:
  print('Categorical data encountered')
else:
  print('\nThere is no categorical data\n\n')


header('NAN DETECTION')
for col in df.select_dtypes(include=[np.number]).columns:
    # Identificar índices con NaN
    nan_mask = df[col].isna()
    nan_indices = np.where(nan_mask)[0]
    n_nans = len(nan_indices)
    if n_nans > 0:
        #Se obtienen valores unicos existentes (menos NaN)
        valid_values = df.loc[~nan_mask, col]
        unique_values = valid_values.unique()
        # Crea una lista de reemplazos distribuyendo cíclicamente entre los valores únicos
        replacements = []
        for i in range(n_nans):
            value_index = i % len(unique_values)
            replacements.append(unique_values[value_index])
        #Asigna los valores de reemplazo a los índices NaN
        for i, idx in enumerate(nan_indices):
            df.iloc[idx, df.columns.get_loc(col)] = replacements[i]
#cantidad de datos perdidos por columna:
conteo=df.isna().sum()

#porcentaje de datos perdidos por columna:
if conteo.sum()==0:
  print('\n\nNo NaN\n\n')
else:
  print(f'There is: {df.isna().sum()/df.shape[0]*100}% of NaN data')
#Dataframe que muestra el porcentaje de los datos perdidos
if conteo.sum()!=0:
  perdidos=pd.DataFrame({'Quantity':df.isna().sum(), 'Percentage':(df.isna().sum()/df.shape[0])*100})
  print(perdidos[perdidos['Quantity']>0].sort_values('Quantity', ascending=False))


header('TEMPORAL DATA:')
#bucle para verificar si tiene datos temporales:
verificar=True
for i in df.columns:
  if not pd.api.types.is_datetime64_dtype(df[i]):
    verificar=False
    break
if verificar:
  print('Temporal data found')
else:
  print('\nTemporal data not found\n\n')


header('OUTLIERS')
def analizar_outliers(df):
    # Crear un DataFrame vacío para almacenar los resultados
    resultados = pd.DataFrame(columns=['Column', 'Lower Bound', 'Upper Bound',
                                      'Outliers Quantity', 'Percentage (%)'])

    # Iterar sobre cada columna y calcular la información de outliers
    for i, columna in enumerate(df.columns):
        #Calculo de los cuartiles
        Q1 = df[columna].quantile(0.25)
        Q3 = df[columna].quantile(0.75)
        IQR = Q3 - Q1
        limbajo = Q1 - 1.5 * IQR#límites
        limalto = Q3 + 1.5 * IQR

        outliers = df[(df[columna] < limbajo) | (df[columna] > limalto)]#se cuentan los outliers
        num_outliers = len(outliers)
        porcentaje = (num_outliers / len(df)) * 100

        resultados.loc[i] = [columna, round(limbajo, 2), round(limalto, 2),
                           num_outliers, round(porcentaje, 2)]
    return resultados

tabla_outliers = analizar_outliers(df)
display(tabla_outliers)


header('COLUMN HISTOGRAMS')
columnas=df.columns.tolist()
gridcol=3
gridfil=math.ceil(len(columnas)/gridcol)
colores = sns.color_palette("husl", len(columnas))
fig = plt.figure(figsize=(5*gridcol, 4*gridfil))
gs = gridspec.GridSpec(gridfil, gridcol, figure=fig, hspace=0.4, wspace=0.4)
for i, col in enumerate(columnas):
    ax = fig.add_subplot(gs[i])
    ax.hist(df[col].dropna(), bins=30, edgecolor='black', color=colores[i])
    ax.set_title(col)
    ax.tick_params(axis='both', labelsize=8)
plt.show()
