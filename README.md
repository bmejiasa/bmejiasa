import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Datos del primer objeto
datos_calcetin = {
    'tiempo': [0.038, 0.063, 0.056, 0.080, 1.10, 0.060, 0.083, 0.075, 0.070, 0.076, 1.01, 1.38, 1.11, 0.056, 1.58],
    'altura': [0.75, 2.42, 2.07, 3.80, 6.70, 2.70, 4.50, 3.60, 2.45, 3.15, 4.80, 8.30, 7.00, 2.10, 9.80]
}

# Datos del segundo objeto
datos_crema= {
    'tiempo': [0.063, 0.075, 0.068, 0.095, 1.30, 0.065, 1.00, 0.090, 0.073, 0.076, 1.08, 1.53, 1.36, 0.065, 1.81],
    'altura': [0.75, 2.42, 2.07, 3.80, 6.70, 2.70, 4.50, 3.60, 2.45, 3.15, 4.80, 8.30, 7.00, 2.10, 9.80]
}

# Convertir a DataFrame de pandas
df_calcetin = pd.DataFrame(datos_calcetin)
df_crema = pd.DataFrame(datos_crema)

# Convertir altura a metros
df_calcetin['altura'] = df_calcetin['altura'] / 100
df_crema['altura'] = df_crema['altura'] / 100

# la regresión lineal y  el gráfico para el primer objeto (calcetin)
sns.regplot(x='altura', y='tiempo', data=df_calcetin, ci=None)
plt.title('Regresión lineal - calcetin')
plt.xlabel('Altura (m)')
plt.ylabel('Tiempo (s)')
plt.show()

# la regresión lineal y el gráfico para el segundo objeto (crema)
sns.regplot(x='altura', y='tiempo', data=df_crema, ci=None)
plt.title('Regresión lineal - crema')
plt.xlabel('Altura (m)')
plt.ylabel('Tiempo (s)')
plt.show()
