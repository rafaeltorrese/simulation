---
marp: true
title: "slides-random-variable"
header: "Variables Aleatorias"
footer: "Simulación"
author: Rafael Torres Escobar
paginate: true
--- 

<!-- _paginate: skip -->

<p class="outstanding-title">Variables Aleatorias</p>

# Definición

- Un modelo de simulación permite lograr un mejor entendimiento de prácticamente cualquier sistema. 
- Resulta indispensable obtener la mejor aproximación a la realidad
- Se  construye un modelo con base en variables aleatorias que interactúen entre sí.
- Las variables aleatorias son aquellas que tienen un comportamiento probabilístico en la realidad. 
- Por ejemplo, el número de clientes que llegan cada hora a un banco depende del momento del día, del día de la semana y de otros factores.

# Características

- La suma de las probabilidades asociadas a todos los valores posibles de la variable aleatoria $x$ es uno.
- La probabilidad de que un posible valor de la variables $x$ se presente siempre es mayor que o igual a cero.
- El valor esperado de la distribución de la variable aleatoria es la media de la misma, la cual a su vez estima la verdadera media de la población.
- Si la distribución de probabilidad asociada a una variable aleatoria está definida por más de un parámetro, dichos parámetros pueden obtenerse mediante un estimador no sesgado. 

# Tipos de variables aleatorias

Las **variables aleatorias** se clasifican en dos grandes categorías: **discretas** y **continuas**, según el tipo de valores que pueden tomar.

 
## Variables Aleatorias Discretas

Estas variables pueden asumir un **número finito o contable de valores distintos**. Los resultados son generalmente números enteros y pueden describir sucesos donde los resultados están claramente definidos y son contables.

- Características:
  - Toman valores específicos y contables (como 0, 1, 2, ...).
  - Existe una función llamada función de probabilidad o de masa de probabilidad, $P(X = x)$, que asigna una probabilidad a cada valor que puede tomar la variable.
  - La **suma de todas las probabilidades** es igual a 1.

---

- Ejemplos:
  - El número de productos defectuosos en una línea de producción.
  - El número de vehículos que llegan a una estación de servicio en una hora.
  - El número de entregas tardías en un mes.

- **Distribución común**: Binomial, Poisson, 

## Ejemplo
Supongamos que una empresa realiza 20 entregas al mes, y estamos interesados en modelar la variable aleatoria que representa el número de entregas que llegan con retraso. El número de entregas tardías, $X$, puede tomar valores discretos como $0, 1, 2, \dots, 20$.


---

### Características:
1. **Valores contables**: Los posibles valores de $X$ son $0, 1, 2, \dots, 20$, ya que la empresa puede tener desde ninguna entrega tardía hasta 20 entregas tardías en un mes.
2. **Función de probabilidad**: Cada valor de $X$ tiene una probabilidad asociada, que puede depender de factores como el desempeño histórico de la empresa o el tráfico durante el mes.
3. **Suma de probabilidades**: La suma de las probabilidades para todos los posibles valores de $X$ debe ser igual a 1. Por ejemplo:
   $$
   P(X = 0) + P(X = 1) + \dots + P(X = 20) = 1
   $$



## Ejemplo concreto
Supongamos que, según datos históricos, la probabilidad de tener 0 entregas tardías es $0.2$, 1 entrega tardía es $0.3$, 2 entregas tardías es $0.25$, 3 entregas tardías es $0.15$, y más de 3 entregas tardías es $0.1$.

- Probabilidad de que haya 0 entregas tardías: $P(X = 0) = 0.2$
- Probabilidad de que haya 1 entrega tardía: $P(X = 1) = 0.3$
- Probabilidad de que haya 2 entregas tardías: $P(X = 2) = 0.25$
- Probabilidad de que haya 3 entregas tardías: $P(X = 3) = 0.15$
- Probabilidad de que haya más de 3 entregas tardías: $P(X > 3) = 0.1$

En este caso, $X$ es una variable aleatoria discreta que modela el número de entregas tardías en un mes.


## Variables Aleatorias Continuas

Estas variables pueden tomar cualquier valor dentro de un intervalo o rango continuo. Los resultados son generalmente números reales, y pueden describir sucesos donde los resultados no son discretos o están limitados a valores contables.

- Características:
  - Pueden tomar cualquier valor en un intervalo de números reales (como 1.5, 2.3, 7.8, ...).
  - Tienen una **función de densidad de probabilidad** (no una función de probabilidad), que describe cómo se distribuyen los valores posibles.
  - La probabilidad de que la variable tome **un valor exacto es 0**, pero se puede calcular la probabilidad de que caiga dentro de un intervalo.

---

- Ejemplos:
  - El tiempo que tarda un camión en completar una entrega.
  - La cantidad de combustible consumido por un vehículo en un trayecto.
  - La longitud o el peso de productos en una línea de producción.

- **Distribución común**: Normal, Exponencial, Uniforme, Weibull.

Un ejemplo de una **variable aleatoria continua** relacionada con la **cadena de suministro** es el **tiempo de entrega de un pedido**.

## Ejemplo
- El tiempo de entrega de un pedido, $T$, puede tomar cualquier valor dentro de un rango de horas o días. 
- No es posible contar con precisión todos los posibles valores de $T$, ya que puede ser, por ejemplo, 3.5 días, 7.2 días, o 15.8 horas. 
- Esto hace que $T$ sea una variable aleatoria continua, ya que puede asumir cualquier valor en un intervalo continuo.

---

### Características:
1. **Valores no contables**: $T$ puede tomar cualquier valor en un intervalo determinado, por ejemplo, entre 1 y 10 días.
2. **Función de densidad de probabilidad**: A diferencia de las variables discretas, aquí se utiliza una función de densidad de probabilidad (PDF) para describir cómo se distribuyen los posibles tiempos de entrega.
3. **Probabilidades en intervalos**: La probabilidad de que el tiempo de entrega sea exactamente un valor (por ejemplo, exactamente 3 días) es prácticamente 0, pero se puede calcular la probabilidad de que esté en un intervalo (por ejemplo, entre 3 y 5).

## Ejemplo concreto

Supongamos que los tiempos de entrega de un pedido se distribuyen normalmente con una media de 5 días y una desviación estándar de 1.5 días. La probabilidad de que un pedido se entregue entre 3 y 7 días se puede calcular utilizando la función de distribución acumulada (FDA) de una distribución normal.

- **Variable aleatoria continua**: $T$ representa el tiempo de entrega de un pedido.
- **Valores posibles**: $T$ puede tomar cualquier valor entre $0$ (entrega instantánea) y $+\infty$, pero en la práctica, se restringe a un rango razonable, como de 1 a 10 días.
- **Distribución**: Una distribución común para modelar este tipo de variable sería la distribución normal.

En este ejemplo, $T$ es una variable aleatoria continua que modela el tiempo de entrega de un pedido en la cadena de suministro.

# Diferencias 
- **Discretas**: Valores contables, función de probabilidad, suelen tratarse con sumas.
- **Continuas**: Valores dentro de intervalos, función de densidad de probabilidad, suelen tratarse con integrales.


# Goodness-of-Fit

- La prueba de **bondad de ajuste** (Goodness-of-Fit) permite determinar si un conjunto de datos sigue una distribución teórica específica. 
- La distribución de probabilidad de los datos históricos puede determinarse mediante las pruebas Chi-cuadrada, de Kolmogorov-Smirnov y de Anderson-Darling. 


## Prueba de Chi-cuadrado (Chi-Squared Test)

La **prueba de Chi-cuadrado** evalúa cómo se ajustan las frecuencias observadas en los datos a las frecuencias esperadas de una distribución teórica.


#### Pasos:
1. **Agrupa los datos**: Divide los datos en intervalos o clases (bins), de modo que cada intervalo tenga una frecuencia observada.
2. **Calcula las frecuencias observadas**: Cuenta cuántos valores de los datos caen en cada intervalo.

---


3. **Calcula las frecuencias esperadas**: Con la distribución teórica seleccionada (por ejemplo, normal), calcula cuántos datos esperarías en cada intervalo.
4. **Aplica la prueba de Chi-cuadrado**: Compara las frecuencias observadas y esperadas para obtener el estadístico $\chi^2$.
5. **Interpreta el valor p**: Si el valor $p$ es menor que $\alpha$ (por ejemplo, 0.05), se rechaza la hipótesis nula de que los datos siguen la distribución teórica.

---

#### Ejercicio


<a href="" target="_blank"></a>
Vamos a realizar un ejercicio con los siguientes datos; <a href="https://www.kaggle.com/datasets/sanjeebtiwary/queue-waiting-time-prediction" target="_blank">Queue Waiting Time Predictions</a>, <a href="https://data.world/city-of-tempe/43b78e73-6f37-49fc-83ef-898a6f87b6b3" target="_blank">311 Caller Wait Time (Performance Measure 2.16)</a>, <a href="https://data.world/makeovermonday/tc-europe-2018-how-long-are-patients-in-an-nhs-ae" target="_blank">
TC Europe 2018: How long are patients in an NHS A&E?</a>, <a href="https://data.world/city-of-ny/fq4m-vjs9" target="_blank">Job Center Wait Time</a>. 

descarga los datos en los siguientes enlaces:

- <a href="https://docs.google.com/spreadsheets/d/1ZoN7Rh79PYCTGjvXifEKHjtMzbHO2J6_/edit?usp=sharing&ouid=101977822223801209851&rtpof=true&sd=true" target="_blank">Queue Waiting Time Prediction (`.xlsx`)</a>
- <a href="https://drive.google.com/uc?id=1xG-aFqcE4Mec5SHsStRJtZuxj9J2W1U0&export=download" target="_blank">Queue Waiting Time Prediction (`.csv`)</a>
- <a href="https://docs.google.com/spreadsheets/d/1RK3FpMnhTnKCwegVw4PpyUPw9tFU3ZCIIEtWIefI3A4/edit?usp=sharing" target="_blank">Queue Waiting Time Prediction (`.gsheets`)</a>
- <a href="https://drive.google.com/uc?id=1_geejJKKDkYy1NltQ0gY6O3t2NUF95Wu&export=download" target="_blank">311 Caller Wait Time (Performance Measure 2.16)</a>
- <a href="https://drive.google.com/uc?id=1VWmlssi71WtMt8FL7XeV1g2I4837xAA0&export=download" target="_blank">TC Europe 2018: How long are patients in an NHS A&E?</a>
- <a href="https://drive.google.com/uc?id=1-wDT4eNU87ewpPqQHSNdD6iXj70ileco&export=download" target="_blank">Job Center Wait Time</a>





---


**Ejemplo en Python**:
```python
from scipy.stats import chisquare
# Frecuencias observadas y esperadas (ejemplo con 4 bins)
observadas = [15, 18, 10, 7]
esperadas = [12, 15, 12, 8]
chi2_stat, p_value = chisquare(observadas, f_exp=esperadas)
print("Estadístico Chi-cuadrado:", chi2_stat, "P-value:", p_value)
```

## Prueba de Kolmogorov-Smirnov (K-S Test)

La **prueba de Kolmogorov-Smirnov** compara la función de distribución acumulada (FDA) empírica de los datos con la FDA teórica de una distribución específica (como normal, exponencial, etc.).

---

#### Pasos:
1. **Define la distribución teórica**: Determina qué distribución deseas probar (por ejemplo, distribución normal con una media y desviación estándar dadas).
2. **Calcula la FDA empírica**: Organiza los datos en orden creciente y calcula su función de distribución acumulada empírica.
3. **Calcula la FDA teórica**: Utiliza la distribución teórica seleccionada para calcular la función de distribución acumulada esperada en cada punto de los datos.
4. **Calcula la distancia máxima**: Encuentra la distancia máxima entre la FDA empírica y la FDA teórica.
5. **Interpreta el valor p**: Si el valor p es mayor que un umbral (generalmente $\alpha = 0.05$), no se rechaza la hipótesis nula, lo que sugiere que los datos siguen la distribución teórica.

---

   **Ejemplo en Python**:
   ```python
   from scipy import stats
   # Datos y ajuste a distribución normal
   datos = [10.5, 12.3, 9.8, 10.2, 11.6]
   ks_stat, p_value = stats.kstest(datos, 'norm', args=(np.mean(datos), np.std(datos)))
   print("K-S Statistic:", ks_stat, "P-value:", p_value)
   ```



## Prueba de Anderson-Darling (A-D Test)

- La **prueba de Anderson-Darling** es una versión más potente de la prueba de Kolmogorov-Smirnov, ya que da más peso a las diferencias en los extremos de la distribución. 
- Esta prueba mide cómo se ajustan los datos a una distribución teórica, como la normal.

---

#### Pasos:
1. **Selecciona la distribución teórica**: Define la distribución contra la que se quieren probar los datos, por ejemplo, normal, exponencial, etc.
2. **Aplica la prueba Anderson-Darling**: Esta prueba devuelve un valor estadístico que mide la desviación de los datos respecto a la distribución teórica.
3. **Interpreta el resultado**: Si el valor estadístico de A-D es mayor que el valor crítico para un nivel de significancia dado ($\alpha$), entonces rechazas la hipótesis de que los datos siguen esa distribución.

---

   **Ejemplo en Python**:
   ```python
   from scipy.stats import anderson
   datos = [10.5, 12.3, 9.8, 10.2, 11.6]
   resultado = anderson(datos, dist='norm')
   print('Estadístico A-D:', resultado.statistic)
   print('Valores críticos:', resultado.critical_values)
   ```



## Comparación de los Métodos

- **Chi-cuadrado**: Utilizada para comparar frecuencias observadas y esperadas. Ideal para variables categóricas o datos agrupados.
- **Kolmogorov-Smirnov (K-S)**: Ideal para comparar la FDA empírica con una distribución teórica. Es general, pero tiene menor sensibilidad en los extremos de la distribución.
- **Anderson-Darling (A-D)**: Similar a K-S pero más sensible en los extremos de la distribución. Es particularmente útil para distribuciones como la normal.

Cada uno de estos métodos proporciona una manera de evaluar si un conjunto de datos sigue una distribución específica. En muchas situaciones, es útil usar una combinación de métodos para obtener una visión más clara del ajuste.

---


<!-- _paginate: skip -->

<p class="outstanding-title">Variables Aleatorias</p>


