# Estructura

1. [Descripción del proyecto](#descripción-del-proyecto)
2. [Planteamiento del problema](#planteamiento-del-problema)
3. [Justificación](#justificación)
4. [Objetivo general](#objetivo-general)
5. [Objetivos específicos](#objetivos-específicos)
6. [Tecnologías propuestas](#tecnologías-propuestas)
7. [Cronograma de desarrollo](#cronograma-de-desarrollo)
8. [Entregables](#entregables)



## Descripción del proyecto 

El proyecto tiene como propósito desarrollar una plataforma web para el análisis y la generación de propuestas de diseñon de distribución de red eléctrica utilizando información geoespacial de los centros poblados del Perú.

La aplicación utilizará datos obtenidos de fuentes oficiales, como GEO GPS Perú, los cuales contienen información geográfica de los centros poblados a nivel nacional. A partir de estos datos, el sistema permitirá seleccionar una ubicación específica mediante filtros como departamento, provincia y distrito u otra clasificación, para construir un grafo representativo de los centros poblados pertenecientes a la zona seleccionada.

Dentro del proceso de optimización, se utilizará la estructura espacial KDTree para realizar búsquedas eficientes de vecinos cercanos, reduciendo la cantidad de conexiones necesarias para la construcción del grafo que va a representar mediante nodos que vendrían a ser los centros poblados. Después de esto se implementarán los algoritmos de Kruskal y Prim para generar árboles de expansión mínima, permitiendo comparar su desempeño mediante métricas como tiempo de ejecución, número de aristas procesadas y longitud total de la red generada.

Los resultados obtenidos serán expuestos mediante una API desarrollada con FastAPI y visualizados en una interfaz web interactiva, permitiendo al usuario explorar los datos geográficos y analizar las redes generadas.

## Planteamiento del problema

El diseño y la planificación de redes eléctricas constituyen una etapa fundamental para garantizar un suministro de energía eficiente, confiable y sostenible. A medida que aumenta la demanda energética y se incorporan nuevas fuentes de generación distribuida y renovable, las redes eléctricas enfrentan el desafío de adaptarse a escenarios cada vez más complejos, donde resulta indispensable optimizar la infraestructura existente y planificar nuevas conexiones de manera eficiente. En este contexto, el empleo de modelos matemáticos y herramientas computacionales permite analizar diferentes alternativas de interconexión, reducir costos asociados a la infraestructura y mejorar la capacidad de planificación del sistema eléctrico. Como señalan Alarcón y Quirós-Tortos (2025), la modernización de las redes eléctricas mediante soluciones tecnológicas y herramientas de optimización contribuye a incrementar la flexibilidad, la resiliencia y la capacidad operativa de estos sistemas.

En el contexto peruano, el crecimiento sostenido de la demanda energética y la amplia distribución geográfica de los centros poblados representan un reto estructural para la planificación de futuras redes de distribución. Según el Ministerio de Energía y Minas [MINEM] (2024), el país cuenta con miles de centros poblados distribuidos en zonas geográficas de difícil acceso e interconexión, situación que ha impulsado la formulación de planes nacionales orientados a reducir las brechas de cobertura eléctrica, especialmente en áreas rurales y aisladas. Para afrontar estos desafíos desde un enfoque computacional, resulta indispensable disponer de información geoespacial confiable y actualizada. En este sentido, GEO GPS Perú constituye una fuente oficial que pone a disposición información geográfica de centros poblados y otras entidades territoriales, proporcionando datos de gran utilidad para el análisis espacial (GEO GPS Perú, 2024). Sin embargo, aunque esta información se encuentra disponible para consulta y descarga, no se identificó una herramienta de libre acceso orientada al análisis geoespacial y a la generación de modelos de interconexión de centros poblados mediante algoritmos de teoría de grafos.

Asimismo, muchas de las implementaciones desarrolladas con fines educativos o de investigación suelen limitarse a conjuntos de datos reducidos o a una única región geográfica, lo que dificulta evaluar el comportamiento de los algoritmos sobre escenarios de mayor escala. Conforme aumenta la cantidad de centros poblados, también crece considerablemente el número de posibles conexiones entre ellos. En un grafo completamente conectado, la cantidad de aristas aumenta de manera cuadrática con respecto al número de nodos, incrementando significativamente el costo computacional para construir modelos de interconexión. Este crecimiento de la complejidad hace inviable evaluar todas las conexiones mediante enfoques tradicionales e introduce la necesidad de incorporar estructuras espaciales que permitan reducir el número de conexiones candidatas antes de la construcción del grafo.

Frente a esta problemática, surge la necesidad de desarrollar una plataforma que integre información geográfica oficial y algoritmos de teoría de grafos para construir modelos de interconexión entre centros poblados. El presente proyecto aborda este desafío mediante el uso de estructuras espaciales, como los árboles k-d (KDTree), para optimizar la construcción del grafo, y algoritmos de árboles de expansión mínima (Minimum Spanning Tree, MST), como Kruskal y Prim, para generar propuestas de redes de distribución aproximadas. La comparación entre ambos algoritmos permitirá analizar su comportamiento sobre grafos construidos a partir de datos geoespaciales reales, evaluando diferencias en tiempos de ejecución y escalabilidad conforme aumenta el tamaño del problema. De esta manera, el proyecto busca ofrecer una plataforma de apoyo para el análisis geoespacial y la experimentación algorítmica sobre datos reales del territorio peruano, facilitando la generación, visualización y evaluación de modelos de interconexión aplicados a distintos escenarios geográficos.

## Justificación

El proyecto busca integrar conocimientos de estructuras de datos, algoritmos, sistemas de información geográfica y desarrollo de software para resolver un problema de carácter práctico mediante herramientas computacionales.

Desde el punto de vista académico, el proyecto permitirá aplicar algoritmos clásicos de teoría de grafos en un contexto real utilizando información geoespacial proveniente de fuentes oficiales sin modificación ni usando datos inventados. La incorporación de una estructura espacial como KDTree permitirá optimizar la construcción del grafo al reducir el número de conexiones candidatas entre centros poblados que representan los nodos, mientras que la implementación de los algoritmos de Kruskal y Prim permitirá comparar su desempeño en términos de eficiencia computacional y calidad de la solución obtenida.

Desde el punto de vista tecnológico, el desarrollo de una API y una interfaz web facilitará la interacción con los datos y la visualización de los resultados, haciendo de esto una herramienta que permita explorar diferentes regiones del país y analizar las redes generadas de manera intuitiva.

De igual manera el proyecto ha sido elaborado con una arquitectura modular, lo que permitirá incorporar nuevas regiones, conjuntos de datos o algoritmos de optimización en futuras versiones sin modificar significativamente la estructura general del sistema.