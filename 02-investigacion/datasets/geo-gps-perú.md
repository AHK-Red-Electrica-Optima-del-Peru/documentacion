# GEO GPS Perú

## Introducción

El desarrollo de modelos de interconexión basados en teoría de grafos requiere información geoespacial confiable que permita representar los diferentes puntos de interés dentro del territorio nacional. En este proyecto, los centros poblados del Perú constituyen la unidad principal de análisis, ya que serán utilizados como nodos para la construcción de los grafos sobre los cuales se aplicarán los algoritmos de optimización.

Con el propósito de obtener esta información, se seleccionó la plataforma **GEO GPS Perú**, la cual cuenta con diferentes conjuntos de datos geoespaciales provenientes de entidades públicas del Estado peruano. Este documento describe las características de dicha plataforma, el conjunto de datos empleado y las razones que justifican su utilización dentro del proyecto.

---

# ¿Qué es GEO GPS Perú?

GEO GPS Perú es una plataforma web orientada a la recopilación y difusión de información geoespacial del territorio peruano. Su principal objetivo es facilitar el acceso a archivos cartográficos y bases de datos espaciales utilizados en diferentes áreas como ingeniería, geografía, planificación territorial, agricultura, minería, medio ambiente e investigación.

La plataforma reúne información proveniente de diversas instituciones públicas, permitiendo descargar datasets en formatos ampliamente utilizados dentro de los Sistemas de Información Geográfica (SIG), como Shapefile (SHP), GeoJSON y otros formatos compatibles con herramientas como QGIS, ArcGIS y bibliotecas de procesamiento geoespacial en Python.

Entre la información disponible se encuentran:

- Centros poblados.
- Límites políticos.
- Red vial.
- Hidrografía.
- Cobertura vegetal.
- Infraestructura educativa.
- Información catastral.
- Otros recursos cartográficos.

---

# Origen de la información

Es importante señalar que GEO GPS Perú no genera la información geoespacial que publica. La plataforma actúa como un medio de difusión que organiza y facilita el acceso a datasets provenientes de diferentes instituciones oficiales del Estado peruano.

Dependiendo del conjunto de datos, las fuentes pueden incluir entidades como:

- Instituto Nacional de Estadística e Informática (INEI).
- Instituto Geográfico Nacional (IGN).
- Ministerio de Educación (MINEDU).
- Ministerio de Desarrollo Agrario y Riego (MIDAGRI).
- Autoridad Nacional del Agua (ANA).
- Otras instituciones públicas.

Esta característica convierte a GEO GPS Perú en un punto de acceso centralizado para información oficial, facilitando la obtención de datos geográficos sin necesidad de consultar múltiples portales gubernamentales.

---

# Dataset utilizado

Para el desarrollo del proyecto se utilizará el conjunto de datos correspondiente a los **Centros Poblados del Perú**, disponible para descarga desde GEO GPS Perú.

Este dataset proporciona la ubicación geográfica de los centros poblados distribuidos en todo el territorio nacional, permitiendo representar cada uno de ellos como un nodo dentro del modelo de interconexión.

En términos generales, el conjunto de datos presenta las siguientes características:

- Cobertura: Nacional.
- Formato principal: Shapefile (SHP).
- Tipo de geometría: Puntos.
- Sistema de referencia geográfica: WGS84.
- Fuente de acceso: GEO GPS Perú.

---

# Información disponible

El dataset contiene información geográfica y administrativa asociada a cada centro poblado.

Entre los principales atributos se encuentran:

| Campo | Descripción |
|--------|-------------|
| Código | Identificador único del centro poblado. |
| Nombre | Nombre del centro poblado. |
| Departamento | Departamento al que pertenece. |
| Provincia | Provincia correspondiente. |
| Distrito | Distrito correspondiente. |
| Categoría | Clasificación del centro poblado. |
| Latitud | Coordenada geográfica. |
| Longitud | Coordenada geográfica. |

Dependiendo de la versión del dataset descargado, pueden existir atributos adicionales relacionados con aspectos administrativos o censales.

---

# Ventajas para el proyecto

La utilización de este conjunto de datos presenta diversas ventajas para el desarrollo del proyecto.

- Cobertura de todo el territorio peruano.
- Información georreferenciada lista para su procesamiento.
- Datos organizados mediante divisiones político-administrativas.
- Compatibilidad con herramientas SIG y bibliotecas de Python.
- Facilidad para realizar filtros por departamento, provincia y distrito.
- Posibilidad de representar cada centro poblado como un nodo dentro de un grafo.

Estas características permiten construir escenarios de prueba con diferentes tamaños y distribuciones geográficas, facilitando el análisis del comportamiento de los algoritmos implementados.

---

# Limitaciones

Aunque el dataset proporciona la ubicación geográfica de los centros poblados, presenta algunas limitaciones para el diseño de redes eléctricas reales.

Entre ellas se encuentran:

- No contiene información sobre líneas eléctricas existentes.
- No incluye la ubicación de subestaciones eléctricas.
- No proporciona datos sobre demanda energética.
- No incorpora información topográfica detallada.
- No considera costos de construcción o mantenimiento.
- No contiene restricciones ambientales o normativas.

Por esta razón, el proyecto utilizará este conjunto de datos únicamente como representación espacial de los nodos del problema, permitiendo desarrollar modelos aproximados de interconexión mediante algoritmos de teoría de grafos.

---

# Relación con el proyecto

Dentro del proyecto, cada centro poblado será representado como un nodo del grafo.

Las coordenadas geográficas permitirán calcular distancias entre los diferentes nodos y construir las conexiones necesarias para la ejecución de los algoritmos de optimización.

Dentro de los dataset que se van a bajar desde esta página, cuentan con columnas de Latitud y de Longitud, lo que permite sacar la distancia euclidiana que es lo que se utilizará para hallar los vecinos más cercanos para cada nodo, es decir para cada centro poblado.

---

# Referencias

- GEO GPS Perú. (2020). *Mapa de centros poblados del Perú*. https://www.geogpsperu.com/

- Instituto Nacional de Estadística e Informática (INEI). https://www.inei.gob.pe/

- Instituto Geográfico Nacional (IGN). https://www.ign.gob.pe/