import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Datos del primer objeto
datos_calcetin = [
    (0.038, 0.75), (0.063, 2.42), (0.056, 2.07), (0.080, 3.80), 
    (1.10, 6.70), (0.060, 2.70), (0.083, 4.50), (0.075, 3.60), 
    (0.070, 2.45), (0.076, 3.15), (1.01, 4.80), (1.38, 8.30), 
    (1.11, 7.00), (0.056, 2.10), (1.58, 9.80)
]

# Datos del segundo objeto
datos_crema = [
    (0.063, 0.75), (0.075, 2.42), (0.068, 2.07), (0.095, 3.80), 
    (1.30, 6.70), (0.065, 2.70), (1.00, 4.50), (0.090, 3.60), 
    (0.073, 2.45), (0.076, 3.15), (1.08, 4.80), (1.53, 8.30), 
    (1.36, 7.00), (0.065, 2.10), (1.81, 9.80)
]

# Convertir a DataFrame de pandas utilizando while
def crear_dataframe(datos):
    df = pd.DataFrame(columns=['tiempo', 'altura'])
    i = 0
    while i < len(datos):
        df.loc[i] = datos[i]
        i += 1
    return df

df_objeto1 = crear_dataframe(datos_calcetin)
df_objeto2 = crear_dataframe(datos_crema)

# Convertir altura a metros utilizando for
def convertir_altura_a_metros(df):
    for i in range(len(df)):
        df.at[i, 'altura'] /= 100

convertir_altura_a_metros(df_calcein)
convertir_altura_a_metros(df_crema)

# Realizar la regresión lineal y trazar el gráfico para el primer objeto
sns.regplot(x='altura', y='tiempo', data=df_calcetin, ci=None)
plt.title('Regresión lineal - calcetin')
plt.xlabel('Altura (m)')
plt.ylabel('Tiempo (s)')
plt.show()

# Realizar la regresión lineal y trazar el gráfico para el segundo objeto
sns.regplot(x='altura', y='tiempo', data=df_crema, ci=None)
plt.title('Regresión lineal - crema')
plt.xlabel('Altura (m)')
plt.ylabel('Tiempo (s)')
plt.show()
