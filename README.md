# Solución a los Ejercicios

## 1. Cálculo del ancho de banda y medio guiado recomendado

El sistema de comunicaciones tiene 17 niveles de señal M = 17  y funciona en banda base. Se debe calcular el ancho de banda máximo si el ruido es despreciable y la tasa de transmisión es de 10 Mbps.

La ecuación de Hartley permite calcular el ancho de banda:

Datos:  
M = 17  
Rb = 10^7 bps  

Fórmula:  
B = Rb / log2(M)  

Cálculo:  
B = 10^7 / log2(17)  
B = 10^7 / 4.09  
B ≈ 2.44 × 10^6 Hz  

Dado que el ancho de banda necesario es 2.44 MHz, se recomienda el uso de cable coaxial o par trenzado de categoría 5e o superior.

---

## 2. Tasa de transmisión máxima en un canal óptico

Se tiene un canal óptico de fibra con las siguientes características:

- Ancho de banda de la fibra: B = 1 THz
- Conversores optoelectrónicos: 100  Gbaudios
- Relación SNR: 15  dB
- Modulación: 4 símbolos en cuadratura M = 4

La tasa de transmisión se obtiene con:

Datos:  
Baudios = 100 × 10^9  
M = 4  

Fórmula:  
Rb = Baudios × log2(M)  

Cálculo:  
Rb = 100 × 10^9 × log2(4)  
Rb = 100 × 10^9 × 2  
Rb = 200 × 10^9 bps  

Por lo tanto, la tasa máxima de transmisión es 200 Gbps.

---

## 3. Efecto de una pérdida del 20% en la fibra óptica

Si se introduce un conector con un 20% de pérdidas, se analizan los siguientes aspectos:

### a) ¿Se verá afectada la tasa de transmisión máxima?

La tasa teórica de transmisión no se modifica porque sigue dependiendo del ancho de banda y la modulación. Sin embargo, la relación señal-ruido efectiva (SNR) disminuirá, lo que puede aumentar la tasa de errores en la recepción.

### b) ¿Qué velocidad máxima se tendrá en la salida?

Si hay una pérdida del 20%, la potencia restante es:

Datos:  
Pérdida = 20%  
Rb = 200 × 10^9 bps  

Cálculo de potencia restante:  
P_salida = 0.8 × P_entrada  

La tasa de transmisión sigue siendo:  
Rb = 200 × 10^9 bps  

La tasa de transmisión sigue siendo de 200 Gbps, pero la calidad de la señal podría reducir la eficiencia de decodificación.

---

## 4. Tipo de modulación y problemas en los diagramas de constelación

Se analizan los diagramas de constelación:

- **A:** Muestra puntos bien definidos, lo que indica una modulación QAM con baja interferencia.
- **B y C:** Presentan dispersión en los puntos, lo que sugiere ruido o interferencias.

Posibles problemas en B y C:
- Mayor dispersión de los puntos, indicando degradación de la señal debido a ruido o interferencias.
- En C, el agrupamiento irregular de los puntos podría ser causado por distorsión de fase o atenuación desigual.

---

## 5. Identificación de modulaciones simultáneas y recuperación de señales

Se transmiten dos señales simultáneamente con modulaciones diferentes.

### a) ¿Qué dos modulaciones se están aplicando?

Es probable que se esté utilizando una combinación de:

- Modulación en Amplitud (AM)
- Modulación en Frecuencia (FM)

o bien una combinación de QAM y PSK.

### b) Recuperación de la información de ambas señales

Para recuperar la información de ambas señales, se deben seguir estos pasos:

1. Aplicar filtros de demodulación adecuados para cada modulación.
2. Separar los componentes en frecuencia y fase para identificar las modulaciones.
3. Utilizar un demodulador AM/FM o un detector de señales I/Q en caso de modulaciones digitales.

---
# **Respuestas a las preguntas**

## **Pregunta 6**  

Las longitudes de onda que se transmiten en cada punto marcado en el esquema son:  

- **Fiber 1**: λ₁  
- **Fiber 2**: λ₂  
- **Fiber 3**: λ₃  
- **Fiber 4**: λ₄  
- **Long-haul shared fiber**: λ₁ + λ₂ + λ₃ + λ₄ (todas combinadas)  

---

## **Pregunta 7**  

Se analiza el encapsulamiento de datos en una pila de 4 capas.  

### **Cálculo del tamaño total del paquete**  

1. **Capa 4**: Envío de 1 KB = 1024 bytes  
2. **Capa 3**: Agrega 256 bytes de cabecera → 1280 bytes  
3. **Capa 3**: Divide en paquetes de 512 bytes  
   - Número de paquetes: 1280 / 512 = 2.5 → Se requieren 3 paquetes  
4. **Capa 2**: Cada paquete de 512 bytes se encapsula con 512 bits (64 bytes)
5. **Capa 2**: El campo de datos es de 128 bytes → 512 / 128 = 4 tramas por paquete  
6. **Capa 1**:  
   - Cada 30 bytes de datos añade 32 bits (4 bytes) de comienzo, 1 byte de parada, y 16 bits de CRC (2 bytes).  
   - Total por cada 30 bytes de datos:  
   30 + 4 + 1 + 2 = 37 bytes
   
Eficiencia = 1024 bytes / 37 = 27.675


---

## **Pregunta 8**  

### **Datos proporcionados:**  
- **Tamaño de bloque**: 1904 bits  
- **Cabecera añadida**: 64 bits  
- **Tiempo de transmisión por trama**: 20 ms  
- **Latencia**: 85 ms  
- **Total de datos a enviar**:

5 MBytes = 5 × 1024 × 1024 × 8 bits = 41943040 bits

Número total de bloques:

41943040 / 1968 ≈ 21307 bloques


### Cálculo del tiempo total de transmisión:  

Cada trama tarda 20 ms, y hay una latencia de 85 ms.  
Tiempo total:  

(21307 × 20 ms) + 85 ms = 426140 ms + 85 ms = 426225 ms = 426.225 s ≈ 7.1 minutos


---

## **Pregunta 9**  

Datos del paquete:  
- Datos: "111110111011010101`  
- Secuencia de inicio de trama: "010101010" 
- Protección Hamming (7,4)  
- Tamaño máximo por trama: 4 bytes (32 bits)  

### Segmentación del paquete:
Se divide en grupos de 4 bits, ya que se usa Hamming (7,4):  

| Datos originales (4 bits) | Código Hamming (7,4) |
|-------------------------|---------------------|
| 1111 | 1111010 |
| 1011 | 1011100 |
| 1010 | 1010011 |
| 1010 | 1010011 |

La trama completa con la secuencia de inicio quedaría:  

010101010 1111010 1011100 1010011 1010011


---

## **Pregunta 10**  

Se usa CRC-8 con el polinomio generador:  

g(x) = x⁸ + x⁷ + x² + 1

### **Cálculo del CRC:**  

1. Se toma la trama de datos y se le agregan 8 bits en cero.  
2. Se realiza la división binaria entre el polinomio generador.  
3. El residuo es el CRC.  
4. Se añade el CRC a la trama para obtener el código final.  

  
---

## **Pregunta 11**  

### Corrección de errores  

- Código H(15,11)  
  - Puede detectar hasta 2 errores.  
  - Puede corregir 1 error.  

- CRC-32  
  - Detecta errores pero no los corrige.  
  - Es capaz de detectar errores de ráfagas de hasta 32 bits.  

---

## **Pregunta 12**  

Se recibe la trama:  

11111111011010101011

Sabemos que:  
- La cabecera es "11111111".  
- Los datos están codificados con Hamming (14,10).  

### Decodificación Hamming (14,10):  

1. Extraemos los datos codificados después de la cabecera:  

011010101011

2. Se aplica el algoritmo de decodificación de Hamming (14,10):  
- Se identifican los bits de paridad.  
- Se verifica la paridad y se corrigen posibles errores.  
- Se extraen los 10 bits de datos originales.  

La respuesta final son los 10 bits útiles que fueron transmitidos.  

---


## 13. ¿A qué protocolo de la capa de enlace de datos corresponde el siguiente esquema temporal?

El esquema mostrado corresponde al Protocolo de Parada y Espera con Acuse de Recibo (Stop-and-Wait ARQ). En este protocolo, el emisor envía una trama y espera el acuse de recibo (ACK) antes de enviar la siguiente. Se observa en el diagrama que cada trama enviada tiene un número de secuencia alternante (0 y 1), y el receptor envía un ACK para cada trama recibida correctamente.

---

## 14. ¿Se puede aplicar el protocolo del ejercicio anterior en el siguiente escenario?

En el segundo escenario se observa la posibilidad de pérdida de tramas. En este caso, si se pierde un ACK o una trama de datos, el protocolo Stop-and-Wait ARQ no funcionaría eficientemente, ya que el emisor quedaría esperando un ACK indefinidamente.

Para este tipo de escenario, un protocolo más robusto como **Go-Back-N o Selective Repeat** sería más adecuado, ya que permiten retransmitir múltiples tramas sin detenerse completamente cuando una se pierde.

---

## 15. Dibujar un diagrama de ventana deslizante con un receptor con buffer para tres tramas y un transmisor que dispone de 5 tramas desordenadas que llegan en el orden 0, 3, 2, 4, 1.

En un protocolo de **ventana deslizante (Sliding Window)** con un buffer de 3 tramas, el receptor puede aceptar tramas fuera de orden hasta su capacidad de buffer.

### **Proceso de recepción:**
1. Llega la trama **0** → Se acepta y se envía ACK 0.
2. Llega la trama **3** → No puede procesarse aún porque falta la 1 y 2.
3. Llega la trama **2** → Se almacena, pero sigue faltando la 1.
4. Llega la trama **4** → No puede procesarse aún.
5. Llega la trama **1** → Ahora se pueden procesar 1 y 2, y el buffer avanza.

Al final, el receptor enviará los ACK correspondientes a medida que recibe y ordena correctamente las tramas.

![image](https://github.com/user-attachments/assets/b951f323-9e88-4e51-bdba-445b4d0b0ac2)


---

## 16. Un canal coaxial con FDM tiene una tasa de transmisión de 500 Mbit/s, una longitud media de trama de 12,584 bits y una tasa de llegada de 20,000 tramas/s.

### **a) ¿Qué retardo tendrá?**
El retardo se puede calcular como:

Retardo = Longitud de trama / Tasa de transmisión
Retardo = 12584 bits / (500 × 10⁶ bits/s)
Retardo = 25.168 µ


### **b) Si lo comparten entre 256 usuarios, ¿cuántas portadoras serán necesarias?**
Dado que se usa multiplexación por división de frecuencia (FDM), cada usuario requiere una portadora. Por lo tanto, si hay 256 usuarios, se necesitan 256 portadoras.

### **c) ¿Cuánto tiempo tardará un nodo en detectar una colisión?**
El tiempo para detectar una colisión en un canal depende de la propagación de la señal y la distancia del canal, que no están especificadas en el problema. Sin embargo, en una red basada en Ethernet, el tiempo de detección suele ser el doble del retardo de propagación en el canal.

Si se diera una longitud de enlace, podríamos calcularlo usando:

T_colisión = 2 × (Longitud del enlace / Velocidad de propagación)

---

## 17. Representar la trama “11111111011010101011” en codificación Manchester y Manchester diferencial.

### **Codificación Manchester:**
- En Manchester, cada bit se representa con una transición en el centro del intervalo de tiempo.
- 1 → Transición de bajo a alto.
- 0 → Transición de alto a bajo.


### **Codificación Manchester diferencial:**
- Se basa en la transición respecto al bit anterior:
  - 1 → No hay transición al inicio del bit.
  - 0 → Se realiza una transición al inicio del bit.

La gráfica sería similar, pero con las transiciones dependientes del bit previo.

---

## 18. Diseñar una red Bluetooth que pueda mantener 15 nodos esclavos activos de manera simultánea.

Bluetooth usa el modelo piconet, donde un maestro puede gestionar hasta 7 esclavos activos simultáneamente. Para lograr 15 nodos activos, se pueden usar dos piconets superpuestas (Scatternet), donde un nodo puede actuar como puente entre ambas.

### **Diseño de la red:**
1. **Dividir los 15 dispositivos en dos piconets**:
   - **Piconet 1**: Un maestro + 7 esclavos activos.
   - **Piconet 2**: Otro maestro + 7 esclavos activos.
   - Un dispositivo puede actuar como puente entre ambas redes.

2. **Configuración del puente**:
   - Un nodo puede pertenecer a ambas redes alternando entre ellas, coordinando la transmisión de datos.

3. **Gestión del tiempo**:
   - Bluetooth usa Time-Division Duplex (TDD), por lo que la sincronización entre los dispositivos y la alternancia del puente son clave para evitar interferencias.

En este modelo, se permite la comunicación entre los 15 nodos sin superar el límite de Bluetooth clásico.

# Respuestas a los Ejercicios de Árbol de Expansión

## Ejercicio 19
**Pregunta:**  
¿Cuál será el rutado entre los siguientes switches si utilizan para su conexión un árbol de expansión con raíz B5?

**Respuesta:**  
Siguiendo el protocolo de árbol de expansión (STP) con B5 como raíz, el rutado se establecerá de la siguiente manera:

- **B5 es la raíz**, por lo que todos los demás switches calcularán su camino más corto hacia B5.
- **Puertos designados y bloqueados**:
  - El switch **B3** seleccionará su camino más corto a B5.
  - **B1 y B2** se conectarán a través de B3 si B3 es el mejor camino.
  - B4 se conectará a B5 directamente si tiene una conexión o a través de B3 o B2 si es necesario.
  - Los enlaces redundantes serán bloqueados según el cálculo de costos STP.

## Ejercicio 20
**Pregunta:**  
Conociendo el rutado del ejercicio anterior, realizar de nuevo el árbol de expansión que se produciría si el switch B3 dejara de estar activo.

**Respuesta:**  
Si el switch **B3** deja de estar activo, se recalculará el árbol de expansión:

- **B1 y B2 buscarán una nueva ruta hacia B5.**
- **B4 deberá establecer su conexión más eficiente hacia B5.**
- **Si B4 y B2 tienen una conexión directa, entonces B2 podría convertirse en la mejor ruta para alcanzar B5.**
- **Se ajustarán los roles de puertos y se bloquearán aquellos que generen bucles.**






