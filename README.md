# TF-PROC.IMAGES

**Estilización de Video en Tiempo Real: Efecto Dibujo Animado**

**Introducción**
En el contexto actual de procesamiento de imágenes y video, la creación de efectos visuales estilizados, como la transformación de video en dibujos animados, ha ganado popularidad. Aplicaciones en redes sociales, cine y animación buscan simplificar o estilizar imágenes y videos para producir efectos visuales atractivos y únicos. El presente proyecto tiene como objetivo desarrollar una aplicación que transforme videos en tiempo real en un estilo de dibujo animado, utilizando técnicas de procesamiento de imágenes como operaciones morfológicas, detección de bordes y binarización.

**Objetivos**

- **General**: Desarrollar una aplicación capaz de estilizar video en tiempo real, aplicando un efecto de dibujo animado a cada fotograma.
- **Específicos**:
  1. Implementar técnicas de procesamiento de imágenes para simplificar y estilizar los fotogramas de video.
  2. Lograr una conversión de video en tiempo real sin comprometer significativamente el rendimiento.
  3. Evaluar la calidad visual y la eficiencia del procesamiento aplicado.

**Desarrollo**
**Descripción del Problema**
En la creación de contenido visual, convertir videos en un estilo de dibujo animado puede mejorar su atractivo y facilitar la creación de contenido artístico. Sin embargo, realizar esta conversión en tiempo real es un desafío debido a las limitaciones de procesamiento y la necesidad de mantener una alta calidad visual.

**Solución Propuesta**
La solución propuesta emplea técnicas de procesamiento de imágenes en Python, utilizando la librería OpenCV. El enfoque principal incluye:

1. **Operaciones Morfológicas**: Para suavizar la imagen y eliminar ruido.
2. **Detección de Bordes**: Para resaltar contornos como en un dibujo.
3. **Binarización**: Para simplificar la imagen en un formato blanco y negro.
   Estas técnicas se aplican en tiempo real a cada fotograma de video, resultando en una secuencia estilizada de video con un efecto de dibujo animado.

**Implementación**
La aplicación se desarrolló en Python, empleando OpenCV para la captura y procesamiento del video. El código está estructurado para leer cada fotograma del video, aplicar las transformaciones necesarias y mostrar y guardar el video estilizado.
