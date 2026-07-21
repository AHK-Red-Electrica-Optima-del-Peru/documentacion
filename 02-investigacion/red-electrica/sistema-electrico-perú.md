# Sistema eléctrico del Perú

## Introducción

El sistema eléctrico peruano es la infraestructura encargada de producir, transportar y distribuir energía eléctrica a los diferentes ciudadanos del país. Su funcionamiento depende de la coordinación entre empresas generadoras, transmisoras, distribuidoras y organismos reguladores, los cuales garantizan la continuidad, seguridad y eficiencia del suministro eléctrico.

Actualmente, la mayor parte del territorio nacional se encuentra integrada al Sistema Eléctrico Interconectado Nacional (SEIN), permitiendo que la energía producida en distintas regiones pueda ser transportada hacia los principales centros de consumo mediante una red de transmisión de alta tensión.

Comprender la estructura general del sistema eléctrico resulta fundamental para este proyecto, ya que permite contextualizar cómo una propuesta de interconexión entre centros poblados puede aproximarse al diseño de una red de distribución utilizando modelos basados en teoría de grafos.

---

## Estructura del sistema eléctrico peruano

El sistema eléctrico puede dividirse en tres etapas principales:

1. Generación.
2. Transmisión.
3. Distribución.

Cada una cumple una función específica dentro del proceso de suministro de energía.

### Generación

La generación consiste en la producción de energía eléctrica mediante diferentes fuentes de energía.

En el Perú, la matriz energética está compuesta principalmente por:

- Centrales hidroeléctricas.
- Centrales termoeléctricas.
- Parques eólicos.
- Plantas solares.

Estas centrales generan la energía que posteriormente será transportada hacia los centros de consumo.

### Transmisión

La transmisión tiene como objetivo transportar grandes cantidades de energía eléctrica desde las centrales generadoras hasta las subestaciones de distribución.

Para ello se utilizan líneas de alta tensión, generalmente de 66 kV, 138 kV y 220 kV, permitiendo reducir las pérdidas de energía durante largas distancias.

Esta etapa constituye la columna vertebral del Sistema Eléctrico Interconectado Nacional (SEIN).

### Distribución

La distribución representa la etapa más cercana al usuario final.

A partir de las subestaciones, la energía es distribuida mediante redes de media y baja tensión hasta llegar a viviendas, industrias, comercios y centros poblados.

Dependiendo de las características del terreno y de la densidad poblacional, las redes de distribución pueden adoptar diferentes configuraciones:

- Redes radiales.
- Redes malladas.
- Redes mixtas.

En zonas rurales predominan las redes radiales debido a su menor costo de implementación.

---

## Organismos que participan en el sistema eléctrico

Diversas instituciones participan en la operación y regulación del sistema eléctrico peruano.

### COES

El Comité de Operación Económica del Sistema Interconectado Nacional (COES) coordina la operación del SEIN, garantizando la seguridad del sistema y la utilización eficiente de los recursos de generación y transmisión.

### Ministerio de Energía y Minas (MINEM)

El MINEM establece las políticas nacionales relacionadas con el desarrollo del sector eléctrico y planifica la expansión de la infraestructura energética del país.

### OSINERGMIN

OSINERGMIN supervisa el cumplimiento de las normas técnicas y regulatorias, además de fiscalizar la calidad y seguridad del servicio eléctrico.

---

## Centros poblados y planificación de redes

Uno de los principales desafíos para la expansión del sistema eléctrico peruano es la gran cantidad de centros poblados distribuidos a lo largo del territorio nacional.

Muchos de estos centros poblados se encuentran en zonas rurales o de difícil acceso, lo que incrementa la complejidad del diseño y expansión de las redes de distribución.

Para facilitar estudios de planificación, diversas instituciones publican información geoespacial sobre la ubicación de estos centros poblados.

En este proyecto se utilizarán los datos proporcionados por **GEO GPS Perú**, los cuales contienen información geográfica oficial que permitirá representar cada centro poblado como un nodo dentro de un grafo.

---

## Relación con el proyecto

Este proyecto se enfoca únicamente en la etapa de distribución de energía eléctrica.

A partir de la ubicación geográfica de los centros poblados, se construirán modelos de interconexión mediante teoría de grafos con el objetivo de generar propuestas de redes de distribución aproximadas.

Es importante señalar que el proyecto **no pretende diseñar una red eléctrica real**, ya que para ello sería necesario considerar variables adicionales como:

- demanda eléctrica
- ubicación de subestaciones
- capacidad de conductores
- topografía
- costos de construcción
- restricciones ambientales
- criterios de confiabilidad

En cambio, el proyecto propone un modelo simplificado donde los centros poblados serán representados como nodos de un grafo y las conexiones entre ellos serán evaluadas mediante algoritmos de optimización.

---

# Referencias

- Comité de Operación Económica del Sistema Interconectado Nacional. (s. f.). https://www.coes.org.pe

- Ministerio de Energía y Minas. (2024). Plan Nacional de Electrificación Rural 2024-2033. https://www.gob.pe/institucion/dger/informes-publicaciones/5003343-plan-nacional-de-electrificacion-rural-pner

- GEO GPS Perú. (2020). Mapa de centros poblados del Perú. https://www.geogpsperu.com/2020/10/mapa-de-centros-poblados-descargar.html

- Ministerio del Ambiente. La generación, transmisión y distribución de electricidad en el Perú.