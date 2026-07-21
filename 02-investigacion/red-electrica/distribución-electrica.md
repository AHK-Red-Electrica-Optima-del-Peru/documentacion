# Redes de distribución eléctrica

## Introducción

Las redes de distribución eléctrica constituyen la etapa final del sistema eléctrico, encargándose de transportar la energía desde las subestaciones de distribución hasta los usuarios finales. Su diseño representa un desafío de ingeniería debido a la necesidad de equilibrar aspectos técnicos, económicos y geográficos, garantizando un suministro seguro, confiable y eficiente.

A diferencia de los sistemas de generación y transmisión, cuyo objetivo es producir y transportar grandes cantidades de energía a largas distancias, las redes de distribución deben adaptarse a las características particulares de cada zona de servicio, considerando la ubicación de los consumidores, la demanda eléctrica, la topografía del terreno y los costos asociados a la infraestructura.

Debido a la complejidad de este proceso, el diseño de redes de distribución suele abordarse como un problema de optimización, donde se busca determinar una configuración que minimice costos y mantenga la calidad del servicio. Este enfoque resulta especialmente relevante para proyectos de electrificación rural, donde la dispersión geográfica de los centros poblados incrementa considerablemente la dificultad de planificación.

---

# ¿Qué es una red de distribución eléctrica?

Una red de distribución eléctrica es el conjunto de instalaciones encargado de suministrar energía eléctrica desde las subestaciones de distribución hasta los consumidores finales, operando generalmente en niveles de media y baja tensión.

Su función principal consiste en distribuir la energía de manera segura y continua, manteniendo parámetros adecuados de calidad del suministro, como niveles de tensión, continuidad del servicio y confiabilidad del sistema.

En términos generales, una red de distribución está conformada por dos niveles:

- **Distribución primaria:** transporta la energía en media tensión desde las subestaciones hacia diferentes sectores o zonas de servicio.
- **Distribución secundaria:** reduce la tensión mediante transformadores y entrega la energía directamente a los usuarios finales.

Aunque cada país posee normas técnicas específicas, los principios de funcionamiento de las redes de distribución son ampliamente aceptados y se encuentran documentados en estándares internacionales como los desarrollados por IEEE e IEC.

---

# Componentes principales

Una red de distribución está formada por diversos elementos que trabajan de manera conjunta para transportar la energía eléctrica hasta los consumidores.

<table>
<thead>
<tr>
<th>Componente</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Subestaciones</strong></td>
<td>Reciben la energía proveniente del sistema de transmisión y reducen el nivel de tensión para alimentar la red de distribución.</td>
</tr>
<tr>
<td><strong>Alimentadores</strong></td>
<td>Líneas de media tensión que distribuyen la energía desde la subestación hacia diferentes sectores.</td>
</tr>
<tr>
<td><strong>Transformadores</strong></td>
<td>Reducen la tensión de media a baja tensión para permitir el suministro a los usuarios.</td>
</tr>
<tr>
<td><strong>Conductores</strong></td>
<td>Transportan la energía eléctrica entre los distintos componentes de la red.</td>
</tr>
<tr>
<td><strong>Usuarios</strong></td>
<td>Consumidores finales de energía eléctrica, como viviendas, comercios, industrias o instituciones.</td>
</tr>
</tbody>
</table>

En un sistema real, cada uno de estos componentes posee características eléctricas específicas relacionadas con capacidad, protección, confiabilidad y mantenimiento. Sin embargo, para fines de modelado computacional, muchos de estos elementos pueden abstraerse y representarse mediante estructuras matemáticas.

---

# Topologías de distribución

La forma en que se conectan los diferentes componentes de una red determina su topología. Cada configuración presenta ventajas y desventajas dependiendo del entorno donde será implementada.

## Red radial

La red radial es la configuración más utilizada en sistemas de distribución rurales. En este esquema existe un único camino entre la subestación y cada usuario.

### Ventajas

- Menor costo de construcción.
- Diseño sencillo.
- Protección más simple.
- Fácil operación y mantenimiento.

### Desventajas

- Baja tolerancia a fallas.
- Una interrupción puede dejar sin servicio a todos los usuarios ubicados aguas abajo.

---

## Red mallada

En una red mallada existen múltiples caminos para transportar la energía entre la fuente y los consumidores.

### Ventajas

- Alta confiabilidad.
- Mayor flexibilidad operativa.
- Permite redistribuir cargas ante fallas.

### Desventajas

- Mayor costo de construcción.
- Sistemas de protección más complejos.
- Mayor dificultad de operación.

---

## Red en anillo

La red en anillo representa una solución intermedia entre una red radial y una mallada.

Generalmente opera como una red radial, pero permite reconfigurar el suministro ante fallas mediante el cierre o apertura de determinados puntos del anillo.

### Ventajas

- Mejor continuidad del servicio.
- Mayor flexibilidad.

### Desventajas

- Mayor complejidad que una red radial.
- Incremento en el costo de implementación.

---

## Redes mixtas

En la práctica, muchas empresas distribuidoras utilizan combinaciones de las topologías anteriores.

Por ejemplo:

- Redes radiales en zonas rurales.
- Redes en anillo en áreas suburbanas.
- Redes malladas en centros urbanos de alta demanda.

La elección depende principalmente de la densidad de carga, el presupuesto disponible, las características geográficas y el nivel de confiabilidad requerido.

---

# Diseño de redes como problema de optimización

El diseño de una red de distribución implica tomar múltiples decisiones para determinar la mejor forma de conectar un conjunto de usuarios con la infraestructura eléctrica existente.

Durante este proceso deben evaluarse diversos criterios, entre ellos:

- Longitud de las líneas.
- Costos de construcción.
- Caída de tensión.
- Pérdidas eléctricas.
- Confiabilidad.
- Demanda proyectada.
- Topografía.
- Facilidad de mantenimiento.
- Posibilidad de expansión futura.

Debido a que estos criterios suelen entrar en conflicto entre sí, el problema se aborda mediante técnicas de optimización que buscan encontrar soluciones capaces de equilibrar el costo de la infraestructura con el desempeño del sistema.

En la literatura científica es común encontrar formulaciones basadas en programación matemática, optimización combinatoria y algoritmos heurísticos para resolver este tipo de problemas.

---

# Modelado mediante teoría de grafos

Desde el punto de vista computacional, una red de distribución puede representarse mediante un grafo ponderado.

En esta representación:

- Los **nodos** representan subestaciones, transformadores o centros poblados.
- Las **aristas** representan posibles conexiones eléctricas entre dichos nodos.
- Los **pesos** representan una métrica asociada a cada conexión, como la distancia, el costo de construcción o una estimación de pérdidas.

Esta representación permite aplicar algoritmos clásicos de teoría de grafos para estudiar diferentes configuraciones de red.

Uno de los modelos más utilizados consiste en construir un **Árbol de Expansión Mínima (Minimum Spanning Tree, MST)**, cuya finalidad es conectar todos los nodos minimizando el peso total de las aristas seleccionadas.

Algoritmos como **Kruskal** y **Prim** permiten obtener este árbol de manera eficiente y constituyen una aproximación ampliamente utilizada como punto de partida para problemas de planificación de redes.

---

# ¿Por qué utilizar un Árbol de Expansión Mínima?

Aunque una red de distribución real incorpora numerosos criterios eléctricos y operativos, un Árbol de Expansión Mínima representa una aproximación adecuada para estudiar el problema desde una perspectiva algorítmica.

Este modelo garantiza que todos los nodos permanezcan conectados utilizando el menor costo acumulado según una métrica determinada, como la distancia geográfica.

En proyectos académicos y de investigación, el MST suele utilizarse como una solución inicial que posteriormente puede enriquecerse con restricciones adicionales relacionadas con capacidad de carga, flujo de potencia, confiabilidad o crecimiento futuro de la red.

---

# Limitaciones del modelo

Un Árbol de Expansión Mínima simplifica considerablemente el problema real de planificación de redes eléctricas.

Entre las principales limitaciones se encuentran:

- No considera la capacidad máxima de los conductores.
- No evalúa caídas de tensión.
- No incorpora pérdidas eléctricas.
- No modela el flujo de potencia.
- No contempla restricciones topográficas o ambientales.
- No considera la demanda eléctrica de cada usuario.
- No incorpora criterios de protección ni coordinación de equipos.
- No incluye redundancia para mejorar la confiabilidad del sistema.

Por estas razones, el MST debe entenderse como una herramienta de análisis y no como un diseño definitivo de una red eléctrica.

---

# Relación con este proyecto

El presente proyecto propone desarrollar una plataforma web para analizar modelos aproximados de redes de distribución eléctrica utilizando información geoespacial de los centros poblados del Perú.

Para ello, cada centro poblado será representado como un nodo del grafo y las posibles conexiones entre ellos como aristas ponderadas por su distancia geográfica.

Con el objetivo de reducir la complejidad computacional durante la construcción del grafo, se empleará la estructura espacial **KDTree**, permitiendo localizar de manera eficiente los vecinos más cercanos de cada nodo y disminuir el número de conexiones candidatas.

Posteriormente, se implementarán los algoritmos **Kruskal** y **Prim** para generar árboles de expansión mínima sobre el grafo construido. Ambos algoritmos serán comparados utilizando métricas como el tiempo de ejecución, la cantidad de aristas procesadas y la longitud total de la red obtenida.

Es importante destacar que la plataforma no pretende diseñar una red eléctrica operativa ni reemplazar las metodologías empleadas por organismos especializados. Su propósito es proporcionar un entorno de experimentación que permita estudiar el comportamiento de algoritmos clásicos de teoría de grafos sobre datos geográficos reales, facilitando el análisis de su rendimiento y escalabilidad en diferentes escenarios del territorio peruano.

