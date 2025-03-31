# Solución a los Ejercicios

## 1. Cálculo del ancho de banda y medio guiado recomendado

El sistema de comunicaciones tiene **17 niveles de señal** (\( M = 17 \)) y funciona en **banda base**. Se debe calcular el **ancho de banda máximo** si el ruido es despreciable y la **tasa de transmisión** es de **10 Mbps**.

La ecuación de Hartley permite calcular el ancho de banda:

\[
B = \frac{R_b}{\log_2 M}
\]

donde:

- \( R_b = 10 \times 10^6 \) bps
- \( M = 17 \)

Sustituyendo valores:

\[
B = \frac{10 \times 10^6}{\log_2(17)}
\]

\[
B = \frac{10 \times 10^6}{4.09}
\]

\[
B \approx 2.44 \text{ MHz}
\]

Dado que el ancho de banda necesario es **2.44 MHz**, se recomienda el uso de **cable coaxial** o **par trenzado de categoría 5e o superior**.

---

## 2. Tasa de transmisión máxima en un canal óptico

Se tiene un **canal óptico de fibra** con las siguientes características:

- **Ancho de banda de la fibra:** \( B = 1 \) THz
- **Conversores optoelectrónicos:** \( 100 \) Gbaudios
- **Relación SNR:** \( 15 \) dB
- **Modulación:** \( 4 \) símbolos en cuadratura (\( M = 4 \))

La tasa de transmisión se obtiene con:

\[
R_b = \text{Baudios} \times \log_2 M
\]

Sustituyendo valores:

\[
R_b = 100 \times 10^9 \times \log_2(4)
\]

\[
R_b = 100 \times 10^9 \times 2
\]

\[
R_b = 200 \text{ Gbps}
\]

Por lo tanto, la **tasa máxima de transmisión** es **200 Gbps**.

---

## 3. Efecto de una pérdida del 20% en la fibra óptica

Si se introduce un **conector con un 20% de pérdidas**, se analizan los siguientes aspectos:

### a) ¿Se verá afectada la tasa de transmisión máxima?

La **tasa teórica de transmisión** no se modifica porque sigue dependiendo del ancho de banda y la modulación. Sin embargo, la **relación señal-ruido efectiva (SNR)** disminuirá, lo que puede aumentar la tasa de errores en la recepción.

### b) ¿Qué velocidad máxima se tendrá en la salida?

Si hay una **pérdida del 20%**, la potencia restante es:

\[
P_{\text{salida}} = 0.8 \times P_{\text{entrada}}
\]

La **tasa de transmisión sigue siendo de 200 Gbps**, pero la calidad de la señal podría reducir la **eficiencia de decodificación**.

---

## 4. Tipo de modulación y problemas en los diagramas de constelación

Se analizan los diagramas de constelación:

- **A:** Muestra puntos bien definidos, lo que indica una modulación **QAM con baja interferencia**.
- **B y C:** Presentan dispersión en los puntos, lo que sugiere **ruido o interferencias**.

Posibles problemas en **B** y **C**:
- Mayor dispersión de los puntos, indicando **degradación de la señal** debido a ruido o interferencias.
- En **C**, el agrupamiento irregular de los puntos podría ser causado por **distorsión de fase o atenuación desigual**.

---

## 5. Identificación de modulaciones simultáneas y recuperación de señales

Se transmiten **dos señales simultáneamente** con **modulaciones diferentes**.

### a) ¿Qué dos modulaciones se están aplicando?

Es probable que se esté utilizando una combinación de:

- **Modulación en Amplitud (AM)**
- **Modulación en Frecuencia (FM)**  

o bien una combinación de **QAM y PSK**.

### b) Recuperación de la información de ambas señales

Para recuperar la información de ambas señales, se deben seguir estos pasos:

1. Aplicar **filtros de demodulación** adecuados para cada modulación.
2. **Separar los componentes** en frecuencia y fase para identificar las modulaciones.
3. Utilizar un **demodulador AM/FM** o un **detector de señales I/Q** en caso de modulaciones digitales.

---

Este documento presenta los cálculos y explicaciones de manera clara para su referencia.
