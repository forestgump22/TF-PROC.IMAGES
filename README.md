# **Informe del Proyecto - TF PROC. IMAGES**

## **Estilización de Video en Tiempo Real: Efecto Dibujo Animado**

### **Introducción**

En el contexto actual de procesamiento de imágenes y video, la creación de efectos visuales estilizados, como la transformación de video en dibujos animados, ha ganado popularidad. Aplicaciones en redes sociales, cine y animación buscan simplificar o estilizar imágenes y videos para producir efectos visuales atractivos y únicos. El presente proyecto tiene como objetivo desarrollar una aplicación que transforme videos en tiempo real en un estilo de dibujo animado, utilizando técnicas de procesamiento de imágenes como operaciones morfológicas, detección de bordes y binarización.

**Tendencias en Animación y Efectos Visuales**

1. **Crecimiento del Mercado**: El mercado de animación y efectos visuales está experimentando un crecimiento significativo. Se espera que alcance los **311,46 mil millones de dólares** para el año 2029, con una tasa de crecimiento anual compuesta del **9,43%** desde 2024[1]. Esto demuestra la creciente demanda de soluciones creativas y visuales en diversas industrias.
2. **Demanda de Calidad Visual**: Los consumidores buscan experiencias visuales de alta definición. Los cinéfilos exigen producciones de alta calidad con efectos visuales atractivos y animaciones realistas[2]. Esto respalda la importancia de la estilización de video para crear efectos visuales impactantes.
3. **Ampliación de Géneros y Plataformas**: Los estudios de animación están ampliando los géneros de contenido que producen. Desde películas animadas 3D-UHD hasta aplicaciones de animación y VFX en televisión, publicidad y juegos, la demanda sigue creciendo [1]. Esto sugiere que la estilización de video tiene un papel crucial en la diversificación de contenidos.

### **Objetivos**

- **General**: Desarrollar una aplicación capaz de estilizar video en tiempo real, aplicando un efecto de dibujo animado a cada fotograma.
- **Específicos**:
  1. Implementar técnicas de procesamiento de imágenes para simplificar y estilizar los fotogramas de video.
  2. Lograr una conversión de video en tiempo real sin comprometer significativamente el rendimiento.
  3. Evaluar la calidad visual y la eficiencia del procesamiento aplicado.

### **Desarrollo**

#### **Descripción del Problema**

En la creación de contenido visual, convertir videos en un estilo de dibujo animado puede mejorar su atractivo y facilitar la creación de contenido artístico. Sin embargo, realizar esta conversión manualmente es muy costoso. Es por eso que se propone hacer la conversión computacionalmente.

#### **Solución Propuesta**

La solución propuesta emplea técnicas de procesamiento de imágenes en Python, utilizando la librería OpenCV. El enfoque principal incluye:

1. **Operaciones Morfológicas**: Para suavizar la imagen y eliminar ruido.
2. **Detección de Bordes**: Para resaltar contornos como en un dibujo.
3. **Binarización**: Para simplificar la imagen en un formato blanco y negro.

Estas técnicas se aplican en tiempo real a cada fotograma de video, resultando en una secuencia estilizada de video con un efecto de dibujo animado.

### Aplicaciones de Segmentación y Detección de Objetos

El procesamiento de imágenes no solo se limita a la estilización de video en tiempo real, sino que también abarca técnicas avanzadas como la segmentación y la detección de objetos.

- **Segmentación:** Permite la identificación precisa de regiones de interés en una imagen, separando objetos del fondo y facilitando el análisis detallado de cada componente visual.

- **Detección de Objetos:** Es fundamental para la identificación y localización automática de múltiples entidades dentro de una escena visual, siendo crucial en aplicaciones como el seguimiento de objetos, la vigilancia automatizada y el reconocimiento de patrones.

Estas técnicas tienen aplicaciones extendidas en diversas industrias, desde la medicina y la seguridad hasta la automoción y la animación. Por ejemplo, en el campo médico, la segmentación de imágenes ayuda en la identificación de estructuras anatómicas en estudios de resonancia magnética, mientras que la detección de objetos es esencial en sistemas de asistencia al conductor para identificar peatones y obstáculos en tiempo real.

La integración de estas técnicas en nuestra aplicación no solo ampliaría sus capacidades funcionales, sino que también mejorarían su adaptabilidad y precisión en diferentes escenarios de uso.

#### **Implementación**

La aplicación se desarrolló en Python, empleando OpenCV para la captura y procesamiento del video. El código está estructurado para leer cada fotograma del video, aplicar las transformaciones necesarias y mostrar y guardar el video estilizado.

Se llevan a cabo los siguientes pasos:

**Captura de Video**:

- Se utiliza la función `cv2.VideoCapture()` para obtener el video de entrada desde la cámara web o un archivo de video.
  
**Preprocesamiento Inicial**:

- Se convierten los fotogramas de video a escala de grises para facilitar el procesamiento (`cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)`).

**Operaciones Morfológicas:**
- Se aplican operaciones morfológicas para mejorar la calidad de la imagen y prepararla para la detección de bordes y binarización.
  - Cierre morfológico (`cv2.morphologyEx(gray, cv2.MORPH_CLOSE, kernel)`) para rellenar pequeños agujeros en los objetos.
  - Apertura morfológica (`cv2.morphologyEx(closed, cv2.MORPH_OPEN, kernel)`) para suavizar los objetos y eliminar el ruido.

**Segmentación y Detección de Objetos:**
- **Segmentación:** Se podrían aplicar técnicas de segmentación como la segmentación basada en umbral (`cv2.threshold()`), aunque en este caso específico se utiliza principalmente para la binarización.
- **Detección de Objetos:** En el contexto de este proyecto, se detectan los bordes y se resaltan sobre la imagen original para crear el efecto de dibujo animado.

**Cálculo del Gradiente Morfológico**:

- Se calcula el gradiente morfológico utilizando la operación `cv2.morphologyEx(opened, cv2.MORPH_GRADIENT, kernel)` para resaltar aún más los bordes y detalles en la imagen.
- Se invierte el gradiente (`cv2.bitwise_not(gradient)`) para obtener bordes blancos sobre un fondo negro.
- Se convierte el gradiente a tres canales (`cv2.cvtColor(gradient_inv, cv2.COLOR_GRAY2BGR)`) para poder aplicarlo a la imagen de color original.

**Binarización y Procesamiento de Imagen:**
- Se aplica la función `cv2.threshold(opened, 120, 255, cv2.THRESH_BINARY_INV)` para binarizar la imagen y obtener una representación en blanco y negro.
- Se combinan los resultados de la binarización y el gradiente para obtener el efecto final de dibujo animado sobre el fotograma original.

**Estilización Final**:

- Finalmente, se combina el fotograma original con el gradiente coloreado utilizando la operación `cv2.bitwise_and(frame, gradient_colored)`, lo que produce el efecto de dibujo animado sobre la imagen de video original.

**Resultados**:

Para evaluar la efectividad del proceso de estilización de video en tiempo real utilizando técnicas de procesamiento de imágenes, se realizó una comparativa utilizando una imagen de muestra de un pájaro. A continuación se presenta la imagen original y la imagen estilizada obtenida mediante una función implementada:

![image](https://github.com/gatitoEsponjosito/TF-PROC.IMAGES/assets/102689608/c21dae30-c5be-4abd-8906-844cf38b81ce)

**Análisis de Resultados**:

La imagen estilizada muestra un efecto visual que simula el estilo de un dibujo animado, caracterizado por líneas más definidas y colores planos. Este resultado se logró aplicando operaciones morfológicas para suavizar y resaltar características, detección de bordes para definir contornos y binarización para simplificar la imagen en blanco y negro. La implementación de estas técnicas permitió transformar la imagen original en una representación estilizada, que puede ser aplicada de manera similar en el procesamiento de video en tiempo real.

### Conclusiones

El proyecto logró desarrollar una aplicación que estiliza video en tiempo real en un estilo de dibujo animado usando técnicas de procesamiento de imágenes. La implementación de operaciones morfológicas, detección de bordes y binarización permitió transformar los fotogramas en tiempo real de manera eficiente.

**Mejoras Potenciales**:

- Explorar el uso de técnicas de aprendizaje profundo para mejorar el estilo de dibujo.
- Implementar ajustes en tiempo real para permitir la personalización del efecto por parte del usuario.
- Mejorar la robustez del sistema para funcionar en diversas condiciones de iluminación y movimiento.

Este proyecto demuestra la capacidad de aplicar técnicas de procesamiento de imágenes para crear efectos visuales innovadores en tiempo real, abriendo posibilidades para aplicaciones en entretenimiento, redes sociales y producción de contenido visual.

**Referencias**:

- [1] Crecimiento del mercado de animación y efectos visuales, tamaño, tendencias y estadísticas de la industria ([mordorintelligence.com](https://www.mordorintelligence.com/es/industry-reports/animation-and-vfx-market))
- [2] Animación y efectos visuales Tendencias del Mercado ([mordorintelligence.com](https://www.mordorintelligence.com/es/industry-reports/animation-and-vfx-market/market-trends))
