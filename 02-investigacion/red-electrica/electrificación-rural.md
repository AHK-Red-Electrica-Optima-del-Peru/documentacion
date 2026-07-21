# Electrificación rural en el Perú

## Introducción

La electrificación rural constituye uno de los principales desafíos para el desarrollo del sistema eléctrico peruano. Debido a la gran cantidad de centros poblados distribuidos en zonas geográficas de difícil acceso, la expansión de la infraestructura eléctrica requiere procesos de planificación que permitan minimizar costos, garantizar la cobertura del servicio y asegurar la viabilidad técnica de las redes de distribución.

En el Perú, este proceso es liderado por el Ministerio de Energía y Minas (MINEM), a través de la Dirección General de Electrificación Rural (DGER), bajo el marco de la **Ley General de Electrificación Rural (Ley N.º 28749)** y del **Plan Nacional de Electrificación Rural (PNER)**. Estos documentos establecen los lineamientos técnicos y estratégicos para ampliar la frontera eléctrica nacional, priorizando la atención de centros poblados rurales, localidades aisladas y zonas de frontera.

Comprender este contexto resulta fundamental para el presente proyecto, ya que proporciona la justificación técnica para utilizar modelos computacionales orientados a la planificación de redes de distribución sobre información geoespacial real.

---

# Marco normativo

La planificación y ejecución de proyectos de electrificación rural en el Perú se encuentra respaldada por un conjunto de normas técnicas y documentos oficiales que establecen los criterios para el diseño de redes eléctricas.

Entre los principales documentos destacan:

- Ley General de Electrificación Rural (Ley N.º 28749).
- Plan Nacional de Electrificación Rural (PNER).
- Guía para la Formulación y Evaluación de Proyectos de Electrificación Rural.
- Código Nacional de Electricidad – Suministro.
- Código Nacional de Electricidad – Sistemas de Distribución.

Estos documentos establecen criterios relacionados con:

- expansión de redes eléctricas;
- evaluación de alternativas de conexión;
- diseño de redes de distribución;
- seguridad y calidad del suministro;
- priorización de proyectos de electrificación.

En conjunto, constituyen el marco técnico sobre el cual se desarrollan los proyectos de ampliación de la infraestructura eléctrica en el país.

---

# La electrificación rural en el Perú

Uno de los principales objetivos del Estado peruano es alcanzar el acceso universal al servicio de energía eléctrica, reduciendo las brechas existentes entre zonas urbanas y rurales.

Para ello, el Ministerio de Energía y Minas desarrolla programas orientados a la construcción y ampliación de redes de distribución que permitan abastecer centros poblados alejados de los principales sistemas eléctricos.

De acuerdo con el **Plan Nacional de Electrificación Rural (PNER)**, la planificación de estos proyectos considera diversos factores, entre ellos:

- ubicación geográfica de las localidades;
- demanda energética proyectada;
- distancia a la infraestructura existente;
- costo de inversión;
- cantidad de beneficiarios;
- evaluación de alternativas tecnológicas.

Estas variables permiten determinar la viabilidad técnica y económica de extender la red eléctrica hacia nuevas localidades.

---

# Situación actual

Durante los últimos años, el Perú ha incrementado progresivamente la cobertura eléctrica en las zonas rurales.

Según información publicada por el Ministerio de Energía y Minas, el coeficiente de electrificación rural alcanzó aproximadamente **86,4 %** al finalizar el año 2024, proyectándose una cobertura cercana al **90,2 %** para julio de 2026 mediante la ejecución de nuevos proyectos de electrificación rural.

Entre las principales iniciativas desarrolladas recientemente destacan:

- ejecución de **9 proyectos de electrificación rural** durante 2024;
- inversión superior a **106 millones de soles**;
- más de **40 000 habitantes beneficiados** en siete regiones del país;

Asimismo, el MINEM anunció la ejecución de:

- **44 proyectos de electrificación rural**;
- inversión superior a **1 185 millones de soles**;
- beneficio para aproximadamente **490 000 habitantes**;
- atención de **5 032 centros poblados** distribuidos en **19 regiones** del país.

Estas cifras evidencian la magnitud del desafío que representa planificar la expansión de redes eléctricas hacia miles de localidades distribuidas en diferentes condiciones geográficas.

---

# Diseño de redes de distribución

El Código Nacional de Electricidad establece que las redes de distribución constituyen la etapa encargada de transportar la energía desde las subestaciones hasta los usuarios finales.

Dependiendo de las características de cada proyecto, las redes pueden adoptar diferentes configuraciones, siendo las más comunes:

- redes radiales;
- redes malladas;
- redes mixtas.

En zonas rurales predominan las configuraciones radiales debido a su menor costo de implementación y mantenimiento, mientras que en áreas urbanas suelen emplearse configuraciones con mayor redundancia para incrementar la confiabilidad del sistema.

Durante la planificación de nuevas redes se consideran aspectos como:

- longitud de los alimentadores;
- ubicación de subestaciones;
- capacidad de transformación;
- niveles de tensión;
- protección del sistema;
- costos de construcción.

---

# Relación con la teoría de grafos

El problema de expansión de redes eléctricas puede modelarse naturalmente mediante teoría de grafos.

En este enfoque:

- los **centros poblados** representan los nodos del grafo;
- las posibles conexiones eléctricas representan las aristas;
- el peso de cada arista puede asociarse a la distancia, el costo de construcción u otra métrica de interés.

El objetivo consiste en determinar una configuración que permita conectar todos los nodos minimizando el costo total de la infraestructura.

Este tipo de formulación coincide con los principios utilizados en los proyectos oficiales de electrificación rural, donde la selección de alternativas depende principalmente de la localización geográfica de las localidades, las distancias entre ellas y los costos asociados a la expansión de la red.

---

# Relación con el proyecto

El presente proyecto no busca diseñar una red eléctrica real ni reemplazar las metodologías utilizadas por el Ministerio de Energía y Minas.

Su propósito es desarrollar una **herramienta de apoyo para el análisis y la experimentación algorítmica**, utilizando información geoespacial de centros poblados del Perú para generar modelos aproximados de interconexión.

Dentro de este contexto:

- cada centro poblado será representado como un nodo del grafo;
- las coordenadas geográficas permitirán calcular distancias entre nodos;
- la estructura **KDTree** será utilizada para acelerar la búsqueda de vecinos cercanos y reducir el número de conexiones candidatas;
- posteriormente, los algoritmos **Kruskal** y **Prim** generarán árboles de expansión mínima (Minimum Spanning Tree, MST), permitiendo comparar su rendimiento y analizar la escalabilidad del modelo conforme aumenta el número de centros poblados.

Es importante señalar que el proyecto constituye una aproximación computacional al problema de planificación de redes de distribución. Por ello, no incorpora variables como demanda eléctrica, topografía, capacidad de conductores, ubicación de subestaciones o restricciones ambientales, las cuales forman parte de los estudios de ingeniería desarrollados durante proyectos reales de electrificación.

---

# Importancia para el proyecto

La investigación sobre la electrificación rural permite comprender el contexto en el cual se desarrollará la plataforma.

Los datos publicados por el MINEM muestran que la expansión de la infraestructura eléctrica continúa siendo un desafío nacional debido al gran número de centros poblados dispersos en el territorio peruano.

En este escenario, el empleo de herramientas computacionales basadas en teoría de grafos puede contribuir al análisis preliminar de diferentes escenarios de interconexión, facilitando la comparación de algoritmos de optimización y el estudio de su comportamiento sobre datos geográficos reales.

---

# Referencias

- Ministerio de Energía y Minas. (2020). Plan Nacional de Electrificación Rural (PNER). Dirección General de Electrificación Rural. https://www.gob.pe/institucion/dger/informes-publicaciones/5003343-plan-nacional-de-electrificacion-rural-pner

- Ministerio de Economía y Finanzas. (s. f.). Guía para la formulación y evaluación de proyectos de electrificación rural. Metodología sectorial MINEM. https://www.mef.gob.pe/contenidos/inv_publica/docs/metodologia_sectorial/MINEM/guia_electrificacion_rural.pdf

- Ministerio de Energía y Minas. (2026, 20 abril). Gobierno se traza la meta de alcanzar 90,2% de cobertura eléctrica en zonas rurales a julio del 2026. https://www.gob.pe/institucion/minem/noticias/1381719-gobierno-se-traza-la-meta-de-alcanzar-90-2-de-cobertura-electrica-en-zonas-rurales-a-julio-del-2026

- Ministerio de Energía y Minas. (2023, 31 diciembre). MINEM lleva energía eléctrica a más de 40 mil peruanos de zonas rurales en siete regiones del país. https://www.gob.pe/institucion/minem/noticias/1026729-minem-lleva-energia-electrica-a-mas-de-40-mil-peruanos-de-zonas-rurales-en

- Ministerio de Energía y Minas. (2025, 25 noviembre). MINEM beneficiará a peruanos con 44 proyectos de electrificación rural. https://minart.pe/2025/11/26/minem-beneficiara-a-peruanos-con-44-proyectos-de-electrificacion-rural/

- Ministerio de Energía y Minas, Dirección General de Electrificación Rural. (s. f.). Dirección General de Electrificación Rural (DGER). https://www.gob.pe/dger

- Ministerio de Energía y Minas; OSINERGMIN. (2001). Código Nacional de Electricidad – Suministro. OSINERGMIN. http://www.osinerg.gob.pe/newweb/uploads/Publico/1.CNE%20SUMINISTRO.pdf

- Ministerio de Energía y Minas; OSINERGMIN. (2006). Código Nacional de Electricidad – Sistemas de Distribución (Tomo IV). OSINERGMIN. http://www.osinerg.gob.pe/newweb/uploads/Publico/2.CNE_TIV%20-%20Sist.de%20Distribucin.pdf

- OSINERGMIN. (2023). Diagramas unifilares de transmisión secundaria. https://www2.osinergmin.gob.pe/publicacionesgrt/pdf/DiagUnifiliar/DIAGUNI2023.pdf

- GEO GPS Perú. (2020, 30 septiembre). Mapa de centros poblados – Descargar shapefile gratis. https://www.geogpsperu.com/2020/10/mapa-de-centros-poblados-descargar.html

- Ministerio de Educación. (2020). Centros poblados – Información espacial. SIGMED. https://sigmed.minedu.gob.pe/descargas/
