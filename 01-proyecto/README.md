# Estructura

1. [Descripción del proyecto](#descripción-del-proyecto)
2. [Planteamiento del problema](#planteamiento-del-problema)
3. [Justificación](#justificación)
4. [Objetivo general](#objetivo-general)
5. [Objetivos específicos](#objetivos-específicos)
6. [Tecnologías propuestas](#tecnologías-propuestas)




## Descripción del proyecto 

El proyecto tiene como propósito desarrollar una plataforma web para el análisis y la generación de modelos de interconexión entre centros poblados del Perú, empleando información geoespacial y algoritmos de teoría de grafos. La plataforma busca ofrecer un entorno que facilite el estudio de propuestas de redes de distribución aproximadas, permitiendo evaluar distintas alternativas de conexión sobre datos geográficos reales.

La aplicación utilizará datos obtenidos de fuentes oficiales, como GEO GPS Perú, los cuales contienen información geográfica de los centros poblados a nivel nacional. A partir de estos datos, el sistema permitirá seleccionar una ubicación específica mediante filtros como departamento, provincia y distrito u otra clasificación, para construir un grafo representativo de los centros poblados pertenecientes a la zona seleccionada.

Con el propósito de mejorar la eficiencia en el procesamiento de la información, el sistema incorporará una estructura espacial basada en árboles k-d (KDTree), la cual permitirá optimizar la búsqueda de centros poblados cercanos y reducir el número de conexiones candidatas durante la construcción del grafo. Sobre dicho grafo se aplicarán los algoritmos de árboles de expansión mínima de Kruskal y Prim para generar propuestas de interconexión, posibilitando además la comparación de su desempeño mediante métricas como el tiempo de ejecución, la cantidad de aristas procesadas y la longitud total de la red obtenida.

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

## Objetivo general
Desarrollar una plataforma web para generar y analizar modelos de interconexión de centros poblados del Perú mediante el uso de información geoespacial y algoritmos de teoría de grafos, esto para poder visualizar propuestas de redes de distribución eléctrica óptimas y comparar el desempeño de diferentes algoritmos de optimización, siendo estos Kruskal y Prim.

## Objetivos específicos

1.  Recolectar, procesar y organizar la información geoespacial de los centros poblados del Perú obtenida de fuentes oficiales, con el fin de contar con un conjunto de datos estructurado para el análisis, sin tener que inventar datos.

2. Diseñar un mecanismo de selección geográfica mediante filtros jerárquicos por departamento, provincia y distrito, que permita delimitar la información utilizada en la generación de modelos de interconexión.

3. Implementar una estructura espacial basada en árboles k-d (KDTree) para optimizar la búsqueda de centros poblados cercanos y reducir el costo computacional en la construcción del grafo.

4. Aplicar los algoritmos de árboles de expansión mínima de Kruskal y Prim para generar propuestas de interconexión entre centros poblados a partir del grafo construido.

5. Comparar el desempeño de los algoritmos de Kruskal y Prim mediante métricas como tiempo de ejecución, cantidad de aristas procesadas y escalabilidad sobre distintos escenarios geográficos.

6. Desarrollar una API que permita gestionar la información geoespacial, ejecutar los algoritmos y exponer los resultados para su consumo por aplicaciones externas.

7. Implementar una interfaz web que permita visualizar los centros poblados, las redes generadas y los resultados de la comparación de algoritmos sobre un mapa interactivo.


## 7. Tecnologías propuestas

Para el desarrollo del proyecto se utilizarán un conjunto de tecnologías orientadas al procesamiento de información geoespacial, la implementación de algoritmos de optimización y el desarrollo de una aplicación web. La selección de cada herramienta responde a criterios de rendimiento, integración y uso de bibliotecas especializadas para el tratamiento de grafos y datos geográficos.

<table>
    <thead>
        <tr>
            <th>Tecnología</th>
            <th>Propósito dentro del proyecto</th>
            <th>Justificación</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>Python</strong></td>
            <td>Lenguaje principal para el desarrollo del backend y la implementación de algoritmos.</td>
            <td>Cuenta con un amplio ecosistema de bibliotecas para ciencia de datos, algoritmos, procesamiento geoespacial y desarrollo de APIs, en este caso FastAPI.</td>
        </tr>
        <tr>
            <td><strong>FastAPI</strong></td>
            <td>Desarrollo de la API REST.</td>
            <td>Permite construir servicios web de alto rendimiento, con documentación automática y una arquitectura moderna basada en Python.</td>
        </tr>
        <tr>
            <td><strong>React + Vite</strong></td>
            <td>Desarrollo de la interfaz web.</td>
            <td>Facilita la creación de interfaces dinámicas e interactivas para la visualización de información geográfica y los resultados de los algoritmos.</td>
        </tr>
        <tr>
            <td><strong>PostgreSQL + PostGIS</strong></td>
            <td>Almacenamiento de información geoespacial.</td>
            <td>Facilita la gestión de datos geográficos y permite realizar consultas espaciales de manera eficiente.</td>
        </tr>
        <tr>
            <td><strong>Pandas</strong></td>
            <td>Procesamiento y limpieza de datos.</td>
            <td>Permite transformar y preparar los datos provenientes de GEO GPS Perú antes de su utilización dentro del sistema.</td>
        </tr>
        <tr>
            <td><strong>SciPy (KDTree)</strong></td>
            <td>Optimización de búsquedas espaciales.</td>
            <td>Proporciona una implementación eficiente del algoritmo KDTree para localizar vecinos cercanos y reducir el número de conexiones candidatas.</td>
        </tr>
        <tr>
            <td><strong>NetworkX</strong></td>
            <td>Construcción y análisis de grafos.</td>
            <td>Facilita la representación de grafos y la implementación de algoritmos clásicos como Kruskal y Prim.</td>
        </tr>
        <tr>
            <td><strong>Git y GitHub</strong></td>
            <td>Control de versiones y gestión del proyecto.</td>
            <td>Permiten mantener un historial del desarrollo, facilitar la colaboración y documentar la evolución del proyecto.</td>
        </tr>
        <tr>
            <td><strong>Docker (opcional)</strong></td>
            <td>Contenerización de la aplicación.</td>
            <td>Facilita el despliegue del backend y garantiza un entorno de ejecución reproducible.</td>
        </tr>
    </tbody>
</table>

Además de las tecnologías mencionadas, el proyecto utilizará información geoespacial proveniente de **GEO GPS Perú** como fuente principal de datos sobre centros poblados del Perú. Estos datos serán procesados para construir modelos de interconexión sobre los cuales se aplicarán técnicas de optimización espacial y algoritmos de teoría de grafos.

Los algoritmos principales considerados para el desarrollo son:

- **KDTree**, empleado para optimizar la búsqueda de vecinos cercanos y reducir el costo computacional durante la construcción del grafo.
- **Kruskal**, utilizado para generar árboles de expansión mínima mediante una estrategia basada en la selección de aristas de menor peso.
- **Prim**, implementado como algoritmo alternativo para la generación de árboles de expansión mínima, permitiendo comparar su desempeño con Kruskal en distintos escenarios geográficos.

