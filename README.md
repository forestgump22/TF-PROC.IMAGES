# **Informe del Proyecto - TF PROC. IMAGES**

## **Estilización de Video en Tiempo Real: Efecto Dibujo Animado, tambien algunas tecnicas/modelos de deep learning para deteccion de objetos y segmentacion**

### **Introducción**

En el contexto actual de procesamiento de imágenes y video, la creación de efectos visuales estilizados, como la transformación de video en dibujos animados, ha ganado popularidad. Aplicaciones en redes sociales, cine y animación buscan simplificar o estilizar imágenes y videos para producir efectos visuales atractivos y únicos. El presente proyecto tiene como objetivo desarrollar una aplicación que transforme videos en tiempo real en un estilo de dibujo animado, utilizando técnicas de procesamiento de imágenes como operaciones morfológicas, detección de bordes por estas operaciones y binarización. Ademas de implementar el uso de algunos modelos de deep learning para segmentacion y deteccion de objetos para la deteccion de personas en zonas prohibidas y la activacion de alarmas.

**Tendencias en Animación y Efectos Visuales**

1. **Crecimiento del Mercado**: El mercado de animación y efectos visuales está experimentando un crecimiento significativo. Se espera que alcance los **311,46 mil millones de dólares** para el año 2029, con una tasa de crecimiento anual compuesta del **9,43%** desde 2024[1]. Esto demuestra la creciente demanda de soluciones creativas y visuales en diversas industrias.

2. **Demanda de Calidad Visual**: Los consumidores buscan experiencias visuales de alta definición. Los cinéfilos exigen producciones de alta calidad con efectos visuales atractivos y animaciones realistas[2]. Esto respalda la importancia de la estilización de video para crear efectos visuales impactantes.

3. **Ampliación de Géneros y Plataformas**: Los estudios de animación están ampliando los géneros de contenido que producen. Desde películas animadas 3D-UHD hasta aplicaciones de animación y VFX en televisión, publicidad y juegos, la demanda sigue creciendo [1]. Esto sugiere que la estilización de video tiene un papel crucial en la diversificación de contenidos.

4. **Aplicaciones de Detección y Segmentación de Objetos**: La inteligencia artificial, especialmente a través del deep learning, ya ha revolucionando la detección de objetos y la segmentación en imágenes. Estas técnicas se podrian utilizar en seguridad y vigilancia, identificando y alertando sobre personas en áreas prohibidas en horarios no autorizados.

### **Objetivos**

- **General**: Desarrollar una aplicación que permita la estilización de videos en tiempo real, transformándolos en un estilo de dibujo animado y utlizar algoritmos avanzados de deep learning ya preentrenados para el uso en la seguridad. Este proyecto tiene como propósito aplicar modelos y/o algoritmos, explorando cómo pueden ser utilizados en aplicaciones prácticas en tiempo real, como la creación de efectos visuales y la mejora de sistemas de seguridad.

- **Específicos**:
  1. Aplicar Operaciones Morfológicas: Implementar operaciones morfológicas avanzadas para la estilización del video, transformándolo en un estilo de dibujo animado.
  2. Aplicar Modelos de Detección de Objetos y Segmentacion: Integrar modelos preentrenados para la detección automática y segmentacion de objetos en la escena del video.

### **Desarrollo**

#### **Descripción del Problema**

En la creación de contenido visual, convertir videos en un estilo de dibujo animado puede mejorar su atractivo y facilitar la creación de contenido artístico. Sin embargo, realizar esta conversión manualmente es muy costoso. Es por eso que se propone hacer la conversión computacionalmente.

#### **Solución Propuesta**

Para lograr la transformación de videos en tiempo real en un estilo de dibujo animado, la solución propuesta utiliza técnicas avanzadas de procesamiento de imágenes implementadas en Python, aprovechando las capacidades de la librería OpenCV. La estrategia incluye los siguientes métodos específicos:

1. **Operaciones Morfológicas**: Se utilizan para suavizar la imagen y eliminar ruido, esenciales para preparar la imagen para un procesamiento más detallado y la creación de efectos de dibujo animado.
2. **Segmentación**: Utiliza modelos de deep learning preentrenados para identificar y segmentar objetos en la escena del video, facilitando su análisis detallado.
3. **Detección de Objetos**: Integra modelos de deep learning preentrenados para la detección automática de objetos, como personas en áreas prohibidas, mejorando la seguridad y vigilancia.

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

**Cálculo del Gradiente Morfológico**:

- Se calcula el gradiente morfológico utilizando la operación `cv2.morphologyEx(opened, cv2.MORPH_GRADIENT, kernel)` para resaltar aún más los bordes y detalles en la imagen.
- Se invierte el gradiente (`cv2.bitwise_not(gradient)`) para obtener bordes blancos sobre un fondo negro.

**Binarización y Procesamiento de Imagen:**

- Se aplica la función `cv2.threshold(opened, 120, 255, cv2.THRESH_BINARY_INV)` para binarizar la imagen y obtener una representación en blanco y negro.
- Se combinan los resultados de la binarización y el gradiente para obtener el efecto final de dibujo animado sobre el fotograma original, tambien hay que decir que obtuvimos problemas en implementar esta version del codigo en formato con webcam, parece que en imagenes funciona mejor que en la webcam, puede correr el codigo para su propia comprobacion.

**Estilización Final**:

- Finalmente, se combina el fotograma original con el gradiente coloreado utilizando la operación `cv2.bitwise_and(frame, gradient_colored)`, lo que produce el efecto de dibujo animado sobre la imagen de video original.

**Resultados**:

Para evaluar la efectividad del proceso de estilización de video en tiempo real utilizando técnicas de procesamiento de imágenes, se realizó una comparativa utilizando una imagen de muestra de un pájaro. A continuación, se presenta la imagen original y la imagen estilizada obtenida mediante una función implementada:

![image](https://github.com/gatitoEsponjosito/TF-PROC.IMAGES/assets/102689608/c21dae30-c5be-4abd-8906-844cf38b81ce)

**Análisis de Resultados**:

La imagen estilizada muestra un efecto visual que simula el estilo de un dibujo animado, caracterizado por líneas más definidas y colores planos. Este resultado se logró aplicando operaciones morfológicas para suavizar y resaltar características, y binarización para simplificar la imagen en blanco y negro. La implementación de estas técnicas permitió transformar la imagen original en una representación estilizada, que puede ser aplicada de manera similar en el procesamiento de video en tiempo real, aunque no se pudo y se dara cuenta que son codigos distinto una el de las imagenes y otro en de la webcam. Esto se aplico distinto debido a que si aplicaba el codigo de las imagenes no funcionaba muy bien con la webcam, tal vez por la luminosidad de las imagenes, es por eso que se aplico algo similar con operaciones morfologicas.

### Conclusiones

El proyecto logró desarrollar una aplicación que estiliza video en tiempo real en un estilo de dibujo animado usando técnicas de procesamiento de imágenes. La implementación de operaciones morfológicas, segmentación y detección de objetos permitió transformar los fotogramas en tiempo real de manera eficiente. Además, se integraron modelos de deep learning que podrian mejorar la seguridad, detectando automáticamente personas en la webcam y segmentando a estas.

**Mejoras Potenciales**:

- Implementar ajustes en tiempo real para permitir la personalización del efecto por parte del usuario.
- Mejorar la robustez del sistema para funcionar en diversas condiciones de iluminación y movimiento.

Este proyecto demuestra la capacidad de aplicar técnicas de procesamiento de imágenes para crear efectos visuales innovadores en tiempo real, abriendo posibilidades para aplicaciones en entretenimiento, redes sociales y producción de contenido visual. Ademas de poder mejorar la seguridad en las casas por temas de robos por mencionar algun ejemplo.

**Referencias**:

- [1] Crecimiento del mercado de animación y efectos visuales, tamaño, tendencias y estadísticas de la industria ([mordorintelligence.com](https://www.mordorintelligence.com/es/industry-reports/animation-and-vfx-market))
- [2] Animación y efectos visuales Tendencias del Mercado ([mordorintelligence.com](https://www.mordorintelligence.com/es/industry-reports/animation-and-vfx-market/market-trends))
