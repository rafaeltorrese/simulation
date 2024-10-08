---
marp: true
title: "slides_evolutionary-algorithms"
header: 'Algoritmos Evolutivos'
footer: 'Inteligencia Artificial'
author: Rafael Torres Escobar
headingDivider: 2
paginate: true
--- 

<p class="outstanding-title">Algoritmos Evolutivos</p>

<!-- _paginate: skip -->

# ¿Qué es la evolución?

- ¿Cómo surgió todo lo que vemos e interactuamos?
- Una forma de explicar esto es la teoría de la evolución. 
- Los organismos vivos que vemos hoy evolucionaron a través de millones de años de cambios sutiles

![bg right:40% w:450 h:400](https://qph.cf2.quoracdn.net/main-qimg-47979e40bff0b801a76eb279227de9f2-pjlq)

---

- La evolución abarca la idea de que en una población de una especie se reproducen pares de organismos. 
- La descendencia es una combinación de los genes de los padres, pero se realizan pequeños cambios en esa descendencia mediante un proceso llamado mutación. 
- Entonces la descendencia pasa a formar parte de la población. 
- Sin embargo, no todos los miembros de una población sobreviven. 


---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310054/artificial-intelligence/04-evolutionary-algorithms/02-peppered-moth.png" class="center" width="800" height="500">

[Evolución de la Polilla Moteada](https://es.wikipedia.org/wiki/Evoluci%C3%B3n_de_la_polilla_moteada)

---

Según la teoría de la evolución darwiniana, una población tiene los siguientes atributos:
- Variedad: los individuos de la población tienen diferentes rasgos genéticos.
- Hereditario: un niño hereda propiedades genéticas de sus padres.
- Selección: mecanismo que mide la aptitud de los individuos. Más fuerte los individuos tienen la mayor probabilidad de supervivencia (supervivencia del más apto).
- Reproducción: por lo general, dos individuos de la población se reproducen para crear descendencia.
- Cruce y mutación: la descendencia creada mediante la reproducción contiene una mezcla de genes de sus padres y tienen ligeros cambios aleatorios en su código genético.

---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310056/artificial-intelligence/04-evolutionary-algorithms/fig-03-example-reproduction-mutation.png" class="center" width="500" height="400">




# Problemas aplicables a algoritmos evolutivos

- Los algoritmos evolutivos no son aplicables para resolver todos los problemas, pero son poderosos para resolver problemas de optimización en los que la solución consiste en una gran cantidad de permutaciones u opciones. 
- Estos problemas suelen consistir en muchas soluciones válidas, algunas de las cuales son mejores que otras. 
- Consideremos el [problema de la mochila](https://docs.google.com/spreadsheets/d/1FF1NCVbgJAHVkdn4qftXcL76bFGn_CkjrhNsNEIyVD4/edit?usp=drive_link), un problema clásico utilizado en informática para explorar cómo funcionan los algoritmos y qué tan eficientes son. 
- En el problema de la mochila, una mochila tiene un peso máximo específico que puede contener.

---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310054/artificial-intelligence/04-evolutionary-algorithms/fig04-knapsack.png" class="center" width="700" height="600">

---

Tenga en cuenta que calificamos **la mejor solución** que podemos encontrar como una solución deseable en lugar de **la solución óptima**. Aunque algunos algoritmos intentan encontrar el verdadero óptimo solución al problema de la mochila, un algoritmo evolutivo intenta encontrar la solución óptima pero **no se garantiza** que la encuentre.

---

- La idea detrás del uso de un algoritmo genético para resolver el problema de la mochila se puede aplicar a una variedad de problemas prácticos. 
- Si una empresa de logística quiere optimizar el embalaje de los camiones en función de sus destinos, por ejemplo, sería útil un algoritmo genético. 
- Si esa misma empresa quisiera encontrar la ruta más corta entre varios destinos, un algoritmo genético también sería útil. 
- Si una fábrica refinara artículos para convertirlos en materia prima a través de un sistema de cinta transportadora y el orden de los artículos influyera en la productividad, un algoritmo genético sería útil para determinar ese orden.


# Optimización Local Vs. Global

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310051/artificial-intelligence/04-evolutionary-algorithms/fig06-global-local.png" class="center" width="700" height="300">

---

Se necesita mucha atención al configurar los parámetros del algoritmo para que se esfuerce por **lograr diversidad** en las soluciones al principio y gravite gradualmente hacia mejores soluciones a lo largo de cada generación. 

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310051/artificial-intelligence/04-evolutionary-algorithms/fig07-diversity-convergence.png" class="center" width="600" height="400">

# Ciclo De Vida de Un AG

- Crear una población: crear una población aleatoria de posibles soluciones.
- Medir la aptitud de los individuos de la población: determinar qué tan bueno es un solución específica es. son.
- Seleccionar padres en función de su condición física: seleccionar pares de padres que reproducir descendencia.
- Reproducir individuos a partir de padres: crear descendencia a partir de sus padres mediante mezclando información genética y aplicando ligeras mutaciones a la descendencia.
- Poblar la próxima generación: seleccionar individuos y descendientes de la Población que sobrevivirá hasta la próxima generación.
  
---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310053/artificial-intelligence/04-evolutionary-algorithms/fig08-life-cycle.png" class="center" width="800" height="400">



# Codificación del Espacio de Soluciones

Cuando utilizamos un algoritmo genético, es primordial realizar el paso de codificación correctamente, lo que requiere un diseño cuidadoso de la representación de posibles estados. El estado es un dato. Estructura con reglas específicas que representa posibles soluciones a un problema. Además, un conjunto de estados forma una población.

## Terminología

Con respecto a los algoritmos evolutivos, una solución candidata individual se denomina **cromosoma**. Un cromosoma está formado por **genes**. El gen es el tipo lógico de la unidad y **el alelo** es el valor real almacenado en esa unidad. Un **genotipo** es una representación de una solución y un **fenotipo** es una solución única en sí misma. Cada cromosoma siempre tiene la **misma cantidad de genes**. Una colección de cromosomas forma una **población**.

---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310052/artificial-intelligence/04-evolutionary-algorithms/fig09-data-structure.png" class="center" width="600" height="400">

---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310051/artificial-intelligence/04-evolutionary-algorithms/fig10-knapsack-encoding.png" class="center" width="600" height="400">


# Creación de Población


<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310053/artificial-intelligence/04-evolutionary-algorithms/fig11-population-solutions.png" class="center" width="700" height="600">



# Medición de la aptitud de los individuos en una población

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310049/artificial-intelligence/04-evolutionary-algorithms/fig12-fitness.png" class="center" width="600" height="400">



# Seleccionar a los padres según su función de adaptación (fitness)

- El siguiente paso en un algoritmo genético es seleccionar padres que producirán nuevos individuos. 
- En la teoría darwiniana, los individuos que están más en forma tienen una mayor probabilidad de reproducción que otros porque normalmente viven más. 
- Además, estos individuos contienen atributos deseables para la herencia debido a su desempeño superior en su entorno.


---

- Una técnica popular para elegir a los padres de acuerdo a su adaptación (fitness) es la selección en la ruleta. 
- Esta estrategia les da a diferentes individuos porciones de una rueda según su condición física. 
- Se “hace girar” la rueda y se selecciona un individuo. 
- Una mayor aptitud física le da al individuo una porción más grande de la rueda. 
- Este proceso se repite hasta alcanzar el número deseado de padres.

---
<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310049/artificial-intelligence/04-evolutionary-algorithms/fig13-selection-each-individual.png" class="center" width="800" height="600">




## Estado estacionario: reemplazar una parte de la población en cada generación.

<img src="https://d.newsweek.com/en/full/2189163/sandwich-generation.webp?w=790&f=b07e4788999b0df4c903a1fe1376f672" class="center" width="600" height="500">


## Generacional: Reemplazar a toda la población en cada generación.

- El modelo generacional crea una cantidad de individuos descendientes igual al tamaño de la población y reemplaza a toda la población con la nueva descendencia.

<img src="https://as2.ftcdn.net/v2/jpg/06/02/56/83/1000_F_602568370_1J7AHYoSdaUthk704G8Mv8KOiGfZCH7I.jpg" class="center" width="400" height="400">


## Rueda de la ruleta: selección de padres e individuos supervivientes

- Los cromosomas con puntuaciones de aptitud más altas tienen más probabilidades de ser seleccionados, pero los cromosomas con puntuaciones de aptitud más bajas todavía tienen una pequeña posibilidad de ser seleccionados. 
- El término selección de rueda de ruleta proviene de una rueda de ruleta de casino que se divide en porciones. 
- Se hace girar la rueda y se suelta una canica en ella. La rebanada seleccionada es aquella en la que cae la canica cuando la rueda deja de girar.

# Reproducción de individuos a partir de padres.

![bg 80%](https://ib.bioninja.com.au/_Media/crossing-over_med.jpeg)
![bg 65%](https://my.clevelandclinic.org/-/scassets/images/org/health/articles/23095-genetic-mutations)


## Cruce de un solo punto: heredar una parte de cada padre

- Se selecciona un punto en la estructura cromosómica. 
- Luego, al hacer referencia a los dos padres en cuestión, se usa la primera parte del primer padre y la segunda parte del segundo padre. 
- Estas dos partes combinadas crean una nueva descendencia. 
  
<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310049/artificial-intelligence/04-evolutionary-algorithms/fig14-crossover.png" class="center" width="700" height="600">


## Cruce de dos puntos: heredar más partes de cada padre

Se seleccionan dos puntos de la estructura cromosómica; luego, haciendo referencia a los dos padres en cuestión, las partes se eligen de manera alterna para formar una descendencia completa.

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310049/artificial-intelligence/04-evolutionary-algorithms/fig15-two-point-crossover.png" class="center" width="700" height="400">

## Cruce uniforme: heredar muchas partes de cada padre

- En el cruce uniforme, se crea una máscara que representa qué genes de cada padre se utilizarán para generar la descendencia. 
- El proceso inverso se puede utilizar para tener una segunda descendencia. La máscara se puede generar aleatoriamente cada vez que se crean descendientes para **maximizar la diversidad**.

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310049/artificial-intelligence/04-evolutionary-algorithms/fig16-uniform-crossover.png" class="center" width="600" height="400">


# Mutación

![bg contain right 80%](https://my.clevelandclinic.org/-/scassets/images/org/health/articles/23095-genetic-mutations)

- La mutación implica cambiar ligeramente los individuos de la descendencia para fomentar la diversidad en la población. 
- Un parámetro de la mutación es **la tasa de mutación**: la probabilidad de que un cromosoma descendiente mute.

## Mutación de cadena de bits para codificación binaria

En la mutación de cadena de bits, un gen de un cromosoma codificado en binario se selecciona aleatoriamente y se cambia a otro valor válido. Otros mecanismos de mutación son aplicables cuando se utiliza codificación no binaria.

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310050/artificial-intelligence/04-evolutionary-algorithms/fig17-bit-sting-mutation.png" class="center" width="600" height="400">

## Mutación  flip-bit para codificación binaria

- En la **mutación flip-bit**, todos los genes de un cromosoma codificado en binario se invierten al valor opuesto.
- Donde había unos hay ceros y donde había ceros hay unos. 
- Este tipo de mutación podría degradar drásticamente las soluciones que funcionan bien y generalmente se usa cuando es necesario introducir diversidad en la población constantemente.

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1701310050/artificial-intelligence/04-evolutionary-algorithms/fig18-flip-bit-mutation.png" class="center" width="700" height="500">

# Poblando la próxima generación

- Cuando se ha medido la aptitud de los individuos de la población y se ha reproducido la descendencia, el siguiente paso es **seleccionar qué individuos** vivirán hasta la siguiente generación. 
- El tamaño de la **población suele ser fijo** y, debido a que se han introducido más individuos mediante la reproducción, algunos deben morir y ser eliminados de la población.
- Puede parecer una buena idea tomar los mejores individuos que se ajusten al tamaño de la población y eliminar el resto. 
- Esta estrategia, sin embargo, podría crear un **estancamiento en la diversidad de individuos** si los individuos que sobreviven son similares en composición genética.

---

<img src="https://res.cloudinary.com/rafaeltorrese/image/upload/v1724766359/artificial-intelligence/04-evolutionary-algorithms/fig04-27.png" class="center" width="800" height="800">


# Exploración versus explotación

- La situación ideal es aquella en la que hay **diversidad de individuos** y la población en su conjunto busca soluciones potenciales tremendamente diferentes en el espacio de búsqueda.
-  Luego **se explotan los espacios de solución local más fuertes** para encontrar la solución más deseable. 
- La belleza de esta situación es que el algoritmo **explora la mayor cantidad posible del espacio de búsqueda** mientras explota **soluciones sólidas** a medida que los individuos evolucionan.


![bg opacity:.1 60%](https://huggingface.co/datasets/huggingface-deep-rl-course/course-images/resolve/main/en/unit1/exp_2.jpg)

<img src="https://huggingface.co/datasets/huggingface-deep-rl-course/course-images/resolve/main/en/unit1/exp_2.jpg" class="center" width="300" height="400">


# Condiciones de parada

- Una condición de parada es la condición que se cumple donde termina el algoritmo; el **individuo más fuerte de la población de esa generación es seleccionado** como la mejor solución.
- La condición de parada más simple es una constante: un valor constante que indica el número de generaciones durante las cuales se ejecutará el algoritmo. 
- Otro enfoque es detenerse cuando se alcanza cierto valor de adaptación. Este método es útil cuando se conoce la aptitud mínima deseada pero se desconoce la solución.

![bg opacity:.1 70%](https://www.mylosscontrolservices.com/Images/mlcs_articles_how-to-calculate-vehicle-stopping-distance_tcm148-21093.jpg)

# Configurar los parámetros de un algoritmo genético

Al diseñar y configurar un algoritmo genético, es necesario tomar varias decisiones que influyen en el rendimiento del algoritmo. 

Las preocupaciones sobre el rendimiento se dividen en dos áreas

1. el algoritmo debe esforzarse por funcionar bien para encontrar buenas soluciones al problema
2. el algoritmo debe funcionar de manera eficiente desde una perspectiva computacional.

![bg opacity:.1 50%](https://res.cloudinary.com/rafaeltorrese/image/upload/v1721253775/artificial-intelligence/04-evolutionary-algorithms/paramter_tuning.jpg)


---

![bg contain right](https://res.cloudinary.com/rafaeltorrese/image/upload/v1721253775/artificial-intelligence/04-evolutionary-algorithms/paramter_tuning.jpg)

- Codificación cromosómica
- Tamaño de la poblacion
- Inicialización de la población
- Número de descendencia
- Método de selección de padres
- Método cruzado
- Tasa de mutación
- Método de mutación
- Métodos de selección de generación.
- Condición de parada
  
# Ejercicio

En esta sección, nos gustaría presentar los detalles de la implementación de los AG con un algoritmo de optimización. 

$$\max f(x) = x * \sin(10 \pi x) + 2.0$$

s.a.

$$-1 \leq x \leq 2$$

La representación binaria de un número real con $l$ genes se realiza de la siguiente manera:

$$x = \frac{\sum_{i = 0}^{l -1} a_i 2^i}{2^l - 1} \times (x_{\max} - x_{\min}) + x_{\min}$$

donde $a_i$ es el alelo de posición $i$, $x_{\max}$ y $x_{\min}$ son las límites superior e inferior del número real

---

Por ejemplo para la representación de un cromosoma que utiliza una cadena binaria de $l = 5$ bits con una precisión $\epsilon = 0.10$, y la siguiente condificación

| index      | 4 | 3 | 2 | 1 | 0 |
|------------|---|---|---|---|---|
| chromosome | 1 | 0 | 0 | 1 | 1 |


nos da un fenotipo $x = 0.83871$ y función de adaptación $f(x) = 2.7865$. El número de bits $l$ se obtiene de la siguiente manera:

$$ l = \left \lceil \log_2 \left(1 + \frac{x_{\max} - x_{\min}}{\epsilon}\right) \right\rceil$$

donde $\epsilon$ es la precisión deseada

---

En este ejmplo utilizaremos los siguientes parámetros:

- Codificación cromosómica: binaria
- Precisión $\epsilon = 0.001$ 
- Tamaño de la poblacion: 10
- Inicialización de la población: Aleatoria $\{0, 1\}$
- Número de descendencia: 10
- Método de selección de padres: Ruleta
- Probabilidad de cruce: 0.40
- Método cruzado: Un solo punto

---


- Probabilidad de Mutar: 0.40
- Tasa de mutación: 0.10
- Método de mutación: Un bit a la vez
- Métodos de selección de generación: Generacional
- Condición de parada: 5 iteraciones

---
Aquí tienes unas instrucciones para implementar un algoritmo genético simple utilizando una hoja de cálculo:

#### Definir la Población Inicial

1. **Crea una hoja en la que definas una población inicial**. 
   - En las columnas, coloca los genes (variables) de los individuos.
   - En las filas, coloca a los individuos. Cada celda contendrá un valor binario (0 o 1) para cada gen.
   - Ejemplo: Si cada individuo tiene 5 genes, crea 5 columnas etiquetadas como Gen1, Gen2, etc. y completa las filas con combinaciones aleatorias de 0s y 1s.

---

#### Calcular la Aptitud (Fitness)
2. **Agrega una columna para la función de aptitud**. 
   - Define una fórmula que evalúe el rendimiento o adecuación de cada individuo.
   - Ejemplo: Si la función de aptitud es maximizar el número de unos.


#### Selección
3. **Realiza la selección para la reproducción**. 
   - Puedes usar métodos como Ruleta o Torneo.
   - Para el método de Ruleta: Calcula la probabilidad de selección dividiendo la aptitud de cada individuo por la suma total de las aptitudes.
   - Usa la función `=RANDBETWEEN(0,1)` para simular la selección de padres basada en la probabilidad.

---

#### Cruce (Crossover)
4. **Implementa el cruce para generar la nueva población**. 
   - Escoge un punto de cruce aleatorio entre los genes de dos padres.
   - Divide el genoma de los padres en dos partes en ese punto y combina la primera parte de un padre con la segunda parte del otro.
   - Usa `=SI(ALEATORIO()<0.5, GenPadre1, GenPadre2)` para cada gen.

#### Mutación
5. **Aplica mutación a algunos genes**.
   - Define una probabilidad baja de mutación (e.g., 0.01).
   - Utiliza `=SI(ALEATORIO()<0.01, 1-GenOriginal, GenOriginal)` para invertir el valor de un gen.

---

#### Reemplazo
6. **Reemplaza la población antigua con la nueva población generada**.
   - Copia los resultados de la cruce y mutación en la tabla original de población.

#### Iterar y Evaluar
7. **Repite el proceso**.
   - Repite los pasos de selección, cruce, mutación y reemplazo para varias generaciones.
   - Evalúa los cambios en la aptitud máxima, mínima y promedio para determinar la convergencia.

---

#### Analizar Resultados
8. **Analiza los resultados obtenidos**.
   - Revisa cómo ha mejorado la aptitud a lo largo de las generaciones.
   - Si es necesario, ajusta los parámetros como la tasa de mutación o el tamaño de la población.

### Consejos Adicionales
- Utiliza gráficos para visualizar la evolución de la aptitud a lo largo de las generaciones.
- Considera la inclusión de operadores adicionales como elitismo para asegurar que los mejores individuos sobrevivan.

# Estrategia de Evolución

Al diseñar una [estrategia de evolución (ES)](https://en.wikipedia.org/wiki/Evolution_strategy), Rechenberg y Schwefel utilizan números reales para representar alelos de genes y hacen de la mutación de distribución normal la técnica de exploración más importante en un panorama de soluciones.

Usaremos el mismo ejemplo del ejercicio para explicar esta estrategia. 

$$\max f(x) = x * \sin(10 \pi x) + 2.0$$

<center>
sujeto a
</center>

$$-1 \leq x \leq 2$$
---

Supongamos que tenemos $\mu$ individuos en la población actual. Para cada individuo,  su cromosoma es $x$, que es un número real en el rango $[-1,2]$. Primero seleccionamos aleatoriamente dos de ellos, $x_1$ y $x_2$, para hacer el cruce y generar una descendencia $x$ como

$$
\begin{equation}
    x = \frac{x_1 +x_2}{2}
\end{equation}
$$

Este operador de cruce se llama cruce intermedio.  

---

- Completamos el cruce $\lambda$ veces para generar $\lambda$ descendencia ($\lambda$ es a menudo mayor que $\mu$). 
- Para cada descendencia, queremos dar una perturbación de distribución normal en cada variable (**el ejemplo tiene solo una variable**).
- Para una distribución normal $N (\xi ,\sigma^2)$ con media $\xi$ y desviación estándar $\sigma$, se puede generar mediante $N ( \xi ,\sigma^2) = \xi + \sigma N(0,1)$, donde $N(0,1)$ es un número aleatorio distribuido normalmente estándar con media 0 y desviación estándar 1.

---

En ES, a menudo queremos hacer cambios para cada variable en función de su valor actual. Por lo tanto, solo usamos $\sigma$ para representar la escala de mutación en ES. Para la $i$-ésima variable $x_i$ de una descendencia, ejecute

$$
\begin{equation}
x_i^{'} = x_i + N_i(0, \sigma^2) = x_i + \sigma N_i(0,1)    
\end{equation}
$$


donde $x^{'}_i$ es el mutante de $x_i$. Al usar la ecuación anterior para cada gen de cada descendencia, podemos obtener nuevos individuos. 

---

- Este operador de mutación se llama mutación normal. Luego, sus valores de aptitud se pueden calcular utilizando la función objetivo. 
- La desviación estándar $\sigma$ puede ser la misma para todas las variables y también puede ser diferente para cada variable, según el diseñador del algoritmo. 
- Luego combinamos $\mu$ individuos actuales y $\lambda$ nuevos individuos y luego elegimos los $\mu$ mejores según sus valores de aptitud para formar una nueva población.



## Implementar la Estrategia de Evolución Con Python

```python
import math
import statistics
import random
from pprint import pprint
```

```python
import numpy as np
import scipy.stats as st
import matplotlib.pyplot as plt
```
---

```python
POPULATION_SIZE = 10
SIGMA = 0.15
INTERVAL = (-1, 2)
NUM_CROSSOVER = POPULATION_SIZE * 2
MAXGEN = 10
TRIALS = 20
```

---

<p class="outstanding-title">Algoritmos Evolutivos</p>

<!-- _paginate: skip -->