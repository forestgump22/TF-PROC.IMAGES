# **Informe del Proyecto - TF PROC. IMAGES**

## **Estilización de Video en Tiempo Real: Efecto Dibujo Animado**

### **Introducción**

En el contexto actual de procesamiento de imágenes y video, la creación de efectos visuales estilizados, como la transformación de video en dibujos animados, ha ganado popularidad. Aplicaciones en redes sociales, cine y animación buscan simplificar o estilizar imágenes y videos para producir efectos visuales atractivos y únicos. El presente proyecto tiene como objetivo desarrollar una aplicación que transforme videos en tiempo real en un estilo de dibujo animado, utilizando técnicas de procesamiento de imágenes como operaciones morfológicas, detección de bordes y binarización.

**Tendencias en Animación y Efectos Visuales**

1. **Crecimiento del Mercado**: El mercado de animación y efectos visuales está experimentando un crecimiento significativo. Se espera que alcance los **311,46 mil millones de dólares** para el año 2029, con una tasa de crecimiento anual compuesta del **9,43%** desde 2024[1]. Esto demuestra la creciente demanda de soluciones creativas y visuales en diversas industrias.
2. **Demanda de Calidad Visual**: Los consumidores buscan experiencias visuales de alta definición. Los cinéfilos exigen producciones de alta calidad con efectos visuales atractivos y animaciones realistas[2]. Esto respalda la importancia de la estilización de video para crear efectos visuales impactantes.
3. **Ampliación de Géneros y Plataformas**: Los estudios de animación están ampliando los géneros de contenido que producen. Desde películas animadas 3D-UHD hasta aplicaciones de animación y VFX en televisión, publicidad y juegos, la demanda sigue creciendo[1]. Esto sugiere que la estilización de video tiene un papel crucial en la diversificación de contenidos.

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

#### **Implementación**

La aplicación se desarrolló en Python, empleando OpenCV para la captura y procesamiento del video. El código está estructurado para leer cada fotograma del video, aplicar las transformaciones necesarias y mostrar y guardar el video estilizado.

### Conclusiones

El proyecto logró desarrollar una aplicación que estiliza video en tiempo real en un estilo de dibujo animado usando técnicas de procesamiento de imágenes. La implementación de operaciones morfológicas, detección de bordes y binarización permitió transformar los fotogramas en tiempo real de manera eficiente.

**Resultados**:

- La calidad visual del efecto de dibujo animado es consistente y añade un atractivo visual significativo.
- La aplicación funciona en tiempo real sin una disminución notable en el rendimiento, aunque podría mejorarse aún más mediante la optimización del procesamiento.

**Mejoras Potenciales**:

- Explorar el uso de técnicas de aprendizaje profundo para mejorar el estilo de dibujo.
- Implementar ajustes en tiempo real para permitir la personalización del efecto por parte del usuario.
- Mejorar la robustez del sistema para funcionar en diversas condiciones de iluminación y movimiento.

Este proyecto demuestra la capacidad de aplicar técnicas de procesamiento de imágenes para crear efectos visuales innovadores en tiempo real, abriendo posibilidades para aplicaciones en entretenimiento, redes sociales y producción de contenido visual.

**Referencias**:

- [1] Crecimiento del mercado de animación y efectos visuales, tamaño, tendencias y estadísticas de la industria ([mordorintelligence.com](https://www.mordorintelligence.com/es/industry-reports/animation-and-vfx-market))
- [2] Animación y efectos visuales Tendencias del Mercado ([mordorintelligence.com](https://www.mordorintelligence.com/es/industry-reports/animation-and-vfx-market/market-trends))
