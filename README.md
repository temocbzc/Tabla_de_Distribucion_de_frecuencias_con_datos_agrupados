# Laboratorio de Estadística · Distribución de frecuencias con datos agrupados

**Herramienta web para construir tablas de distribución de frecuencias de datos agrupados en intervalos de clase, con los cálculos paso a paso, y descargarlas como imagen JPG.**

🔗 **Usar la herramienta:** https://temocbzc.github.io/Tabla_de_Distribucion_de_frecuencias_con_datos_agrupados/

🔗 **Módulo anterior (datos no agrupados):** https://temocbzc.github.io/Tabla_de_Distribucion_de_frecuencias_sin_datos_agrupados/

---

## Sobre el Laboratorio de Estadística

Este módulo es parte del **Laboratorio de Estadística**, un proyecto de herramientas digitales abiertas para los cursos de **Estadística y Probabilidad I y II** de nivel bachillerato, pensado especialmente para el **Colegio de Ciencias y Humanidades (CCH) de la UNAM**.

El laboratorio sigue la propuesta del Programa de Estudios 2024 del CCH, que pide incorporar la computadora y las herramientas tecnológicas para organizar datos, calcular medidas y construir gráficas. La intención es que el tiempo de clase se dedique a **analizar e interpretar** la información y no a hacer cálculos repetitivos a mano.

---

## Este módulo: tabla de distribución de frecuencias con datos agrupados

**Ubicación en el programa:** Estadística y Probabilidad I · Unidad 1, *Análisis de información estadística para una variable* · Representación tabular.

### Cuándo agrupar los datos

Se agrupan los datos en intervalos de clase cuando la variable es **cuantitativa** y tiene **muchos valores distintos**, por ejemplo estaturas, pesos, tiempos o calificaciones con decimales. Si la variable tiene pocos valores distintos, conviene usar la tabla de [datos no agrupados](https://temocbzc.github.io/Tabla_de_Distribucion_de_frecuencias_sin_datos_agrupados/).

### Qué hace

1. Recibe los datos de una muestra, ya sea en un **archivo CSV** o escritos directamente en la página.
2. Muestra los **cálculos paso a paso**: rango, número de clases, amplitud y límites de los intervalos.
3. Construye la tabla de distribución de frecuencias con datos agrupados.
4. Genera una imagen **JPG** en alta resolución, lista para una presentación, un reporte o una tarea.

Está diseñada para usarse desde el **celular**.

### Procedimiento

**1. Rango de la muestra**

$$R = x_{\text{máx}} - x_{\text{mín}}$$

**2. Número de clases (regla de Sturges)**

$$k = 1 + 3.322 \log(n)$$

Si el resultado no es entero, se aproxima al **entero siguiente**.

**3. Amplitud de los intervalos**

$$A = \frac{R}{k}$$

El resultado se aproxima **hacia arriba**, con el **mismo número de decimales que tienen los datos**. Así se garantiza que los intervalos abarquen todos los datos de la muestra.

**4. Límites de los intervalos**

- El primer límite inferior es el dato menor: $LI_1 = x_{\text{mín}}$.
- Cada límite superior se obtiene sumando la amplitud: $LS_i = LI_i + A$, y $LI_{i+1} = LS_i$.
- Los intervalos son **semiabiertos** $[LI_i,\ LS_i)$: el límite inferior se incluye y el superior no.
- El **último intervalo es cerrado** $[LI_k,\ LS_k]$, para que incluya al dato mayor.

**Ejemplo** con las 50 estaturas del archivo de ejemplo:

| Paso | Cálculo |
|---|---|
| Rango | $R = 1.77 - 1.47 = 0.30$ |
| Número de clases | $k = 1 + 3.322 \log(50) = 6.64 \rightarrow k = 7$ |
| Amplitud | $A = 0.30 / 7 = 0.0429 \rightarrow A = 0.05$ (2 decimales, como los datos) |
| Primer intervalo | $[1.47,\ 1.52)$ |
| Último intervalo | $[1.77,\ 1.82]$ |

### Columnas de la tabla

| Símbolo | Nombre | Cálculo |
|:---:|---|---|
| $i$ | Número de clase | Enumeración de los intervalos |
| $LI_i$ | Límite inferior | Se incluye en el intervalo ( **[** ) |
| $LS_i$ | Límite superior | No se incluye ( **)** ), excepto en el último intervalo ( **]** ) |
| $x_i$ | Marca de clase | $\dfrac{LI_i + LS_i}{2}$ |
| $f_i$ | Frecuencia absoluta | Número de datos dentro del intervalo |
| $fr_i\ \%$ | Frecuencia relativa porcentual | $\dfrac{f_i}{n}\times 100$ |
| $F_i$ | Frecuencia absoluta acumulada | $f_1 + f_2 + \dots + f_i$ |
| $Fr_i\ \%$ | Frecuencia relativa acumulada porcentual | $fr_1 + fr_2 + \dots + fr_i$ |

### Modo "Elegir k y A"

Además de la regla de Sturges, los alumnos pueden escribir **su propio número de clases** $k$ y **su propia amplitud** $A$. Esto permite:

- Comparar cómo cambia la tabla con más o menos clases.
- Comprobar qué pasa cuando los intervalos **no alcanzan** al dato mayor: la herramienta avisa cuántos datos quedaron fuera.

### Formato del archivo CSV

- La **celda A1** lleva el **nombre de la variable**.
- Debajo, en la misma columna, van **todos los datos**, uno por celda.
- En Excel o Google Sheets: *Archivo → Guardar como / Descargar → CSV*.

```
Estatura (m)
1.61
1.67
1.61
1.60
1.56
```

En el repositorio hay un archivo de ejemplo: [`ejemplo_estaturas.csv`](ejemplo_estaturas.csv).

### Privacidad

Los datos se procesan **solo en el navegador** del usuario. No se envían ni se guardan en ningún servidor.

---

## Actividades sugeridas para el aula

1. **Construir a mano y verificar.** Calcular $R$, $k$ y $A$ en el cuaderno, construir la tabla y comprobarla con la herramienta. El apartado *Ver datos ordenados* ayuda a contar los datos de cada intervalo.
2. **Cambiar el número de clases.** Construir la tabla con $k = 4$, con el valor de Sturges y con $k = 12$. ¿Qué información se pierde con pocas clases? ¿Qué problema aparece con demasiadas?
3. **Leer la tabla.**
   - ¿En qué intervalo hay más datos?
   - ¿Qué porcentaje de la muestra es menor que cierto límite superior? ¿En qué columna se lee directamente?
   - ¿Por qué no se puede saber, solo con la tabla, cuál fue el dato exacto más repetido?
4. **Datos propios.** Medir en el grupo una variable continua (estatura, tiempo de traslado, horas de sueño) y construir su tabla.

---

## Mapa del laboratorio

| Módulo | Estado |
|---|:---:|
| [Distribución de frecuencias, datos no agrupados](https://temocbzc.github.io/Tabla_de_Distribucion_de_frecuencias_sin_datos_agrupados/) | ✅ Disponible |
| Distribución de frecuencias, datos agrupados | ✅ Disponible |
| Gráficas: barras, circular, histograma, polígono de frecuencias, ojiva | 🔜 Planeado |
| Medidas de tendencia central, dispersión y posición | 🔜 Planeado |
| Datos bivariados: tablas de contingencia, correlación y regresión | 🔜 Planeado |
| Azar y probabilidad: simulación y probabilidad condicional | 🔜 Planeado |
| Distribuciones binomial y normal, Teorema del Límite Central, inferencia | 🔜 Planeado |

---

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `index.html` | Herramienta web (un solo archivo, sin dependencias que instalar) |
| `ejemplo_estaturas.csv` | 50 estaturas de ejemplo para probar la herramienta |

---

## Autor

**Dr. Ignacio Cuauhtémoc Benítez Zúñiga** · Profesor de Estadística y Probabilidad, Colegio de Ciencias y Humanidades, UNAM.

Proyecto desarrollado dentro del trabajo sobre el uso de la inteligencia artificial generativa en la enseñanza de la estadística en el bachillerato.

## Referencia

Colegio de Ciencias y Humanidades, UNAM (2024). *Programas de Estudio. Área de Matemáticas. Estadística y Probabilidad I–II.* https://cch.unam.mx/sites/default/files/programas2024/ESTADISTICA_PROBABILIDAD_I_II.pdf
