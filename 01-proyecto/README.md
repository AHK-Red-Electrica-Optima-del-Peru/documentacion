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

El diseño y la planificación de redes eléctricas constituyen una etapa fundamental para garantizar un suministro de energía eficiente, confiable y sostenible. A medida que aumenta la demanda energética y se incorporan nuevas fuentes de generación distribuida y renovable, las redes eléctricas enfrentan el desafío de adaptarse a escenarios cada vez más complejos, donde resulta indispensable optimizar la infraestructura existente y planificar nuevas conexiones de manera eficiente. En este contexto, el empleo de modelos matemáticos y herramientas computacionales permite analizar diferentes alternativas de interconexión, reducir costos asociados a la infraestructura y mejorar la capacidad de planificación del sistema eléctrico. Como señalan Alarcón y Quirós-Tortos (2025), la modernización de las redes eléctricas mediante soluciones tecnológicas y herramientas de optimización contribuye a incrementar la flexibilidad, resiliencia y capacidad operativa de estos sistemas.

En el contexto peruano, el crecimiento sostenido de la demanda energética y la amplia distribución geográfica de los centros poblados representan un reto para la planificación de futuras redes de distribución. Si bien existen fuentes oficiales, como GEO GPS Perú, que proporcionan información geoespacial sobre la ubicación de los centros poblados, dichos datos no se encuentran acompañados de herramientas que permitan analizarlos desde una perspectiva de optimización espacial o utilizarlos para generar modelos de interconexión que sirvan como apoyo en estudios académicos y de investigación.

Asimismo, muchas de las implementaciones desarrolladas con fines educativos o de investigación suelen limitarse a conjuntos de datos reducidos o a una única región geográfica, dificultando la comparación de algoritmos y el análisis de su comportamiento sobre diferentes escenarios. Esta limitación impide evaluar cómo varía el rendimiento de los algoritmos conforme aumenta la cantidad de nodos o cambia la distribución espacial de los centros poblados.

Frente a esta problemática, surge la necesidad de desarrollar una plataforma que integre información geográfica oficial y algoritmos de teoría de grafos para construir modelos de interconexión entre centros poblados, permitiendo generar y visualizar propuestas de redes de distribución aproximadas, así como comparar el desempeño de diferentes algoritmos de árboles de expansión mínima mediante métricas de rendimiento computacional. De esta manera, el proyecto busca ofrecer una herramienta que facilite el análisis geoespacial y la experimentación algorítmica sobre datos reales del territorio peruano.

## Justificación

El presente proyecto busca integrar conocimientos de estructuras de datos, algoritmos, sistemas de información geográfica y desarrollo de software para resolver un problema de carácter práctico mediante herramientas computacionales.

Desde el punto de vista académico, el proyecto permitirá aplicar algoritmos clásicos de teoría de grafos en un contexto real utilizando información geoespacial proveniente de fuentes oficiales. La incorporación de una estructura espacial como KDTree permitirá optimizar la construcción del grafo al reducir el número de conexiones candidatas entre centros poblados, mientras que la implementación de los algoritmos de Kruskal y Prim permitirá comparar su desempeño en términos de eficiencia computacional y calidad de la solución obtenida.

Desde el punto de vista tecnológico, el desarrollo de una API y una interfaz web facilitará la interacción con los datos y la visualización de los resultados, proporcionando una herramienta que permita explorar diferentes regiones del país y analizar las redes generadas de manera intuitiva.

Asimismo, el proyecto ha sido concebido con una arquitectura modular, lo que permitirá incorporar nuevas regiones, conjuntos de datos o algoritmos de optimización en futuras versiones sin modificar significativamente la estructura general del sistema.