# Transición hacia Energías Renovables

Análisis de la adopción global de energías renovables y de los factores asociados a su avance, desarrollado como proyecto final del Módulo 8 "Comunicación de resultados" del "Diplomado Introducción Analítica a la Ciencia de Datos".

**Sitio del proyecto:** https://axeleduardoalvaradoarce.github.io/Proyecto_Equipo2/

---

## Descripción del proyecto

El proyecto estudia la transición energética a nivel mundial con dos preguntas de investigación:

1. **¿Qué países han realizado las transiciones más rápidas hacia el uso de energías renovables?**
2. **¿Qué factores están relacionados con una mayor adopción de energías renovables?**

Definimos la "penetración renovable" como la proporción de electricidad generada a partir de fuentes renovables (excluyendo la hidroeléctrica) respecto a la generación eléctrica total. El análisis combina exploración de datos y un modelo de regresión con regularización Lasso (comparado con Ridge), sobre un panel de 78 países durante el periodo 1990–2025.

## Fuentes de datos

- **Statistical Review of World Energy (Energy Institute)**: Contiene información energética (TES per cápita, generación renovable sin hidroeléctrica, generación eléctrica total).
- **Banco Mundial**: Contiene el PIB per cápita en paridad de poder adquisitivo.

## Entregables

- **Reporte** del proyecto (documento con problema, metodología, modelo, resultados y conclusiones).
- **Dashboard** interactivo con los principales resultados.
- **Sitio web** que reúne todo lo anterior.

### `.github/workflows/`

Contiene la automatización que publica el sitio.

| Archivo | Descripción |
|---|---|
| `publish.yml` | Flujo de GitHub Actions que construye y publica el sitio en GitHub Pages cada vez que se sube un cambio a la rama `main`. Instala Quarto, R y Python 3.12, instala las librerías de `requirements.txt`, renderiza el sitio con `quarto render` y lo despliega en GitHub Pages. |

### `Documentos/`

Contiene las Bases de datos que utilizamos, los cuatro archivos originales, tal como se descargaron de sus fuentes, y la base unificada que resulta de su limpieza e integración.

| Archivo | Descripción | Fuente |
|---|---|---|
| `Proyecto_Transicion_Hacia_Energias_Renovables.ipynb` | Notebook con el análisis completo: obtención y limpieza de los datos, análisis exploratorio, cálculo de la penetración renovable y de la velocidad de transición, modelos Lasso y Ridge, diagnóstico y proyección a 2035. | — |
| `tes_per_capita_raw.csv` | Suministro total de energía por habitante, en gigajoules (GJ). | Energy Institute, *Statistical Review of World Energy* (hoja "TES per capita") |
| `renovables_excl_hidro_raw.csv` | Generación de electricidad con fuentes renovables, excluyendo la hidroeléctrica, en teravatios-hora (TWh). | Energy Institute, *Statistical Review of World Energy* (hoja "Ren power (excl hydro) - TWh") |
| `generacion_electrica_raw.csv` | Generación total de electricidad, en teravatios-hora (TWh). | Energy Institute, *Statistical Review of World Energy* (hoja "Electricity Generation - TWh") |
| `pib_per_capita_ppp_raw.csv` | PIB per cápita en paridad de poder adquisitivo (PPA), en dólares internacionales corrientes. | Banco Mundial, Indicadores del Desarrollo Mundial (NY.GDP.PCAP.PP.CD) |
| `datos.csv` | Base de datos final, obtenida tras limpiar e integrar las cuatro fuentes, con una observación por país y año. | Elaboración propia |

El Statistical Review of World Energy es la fuente que utiliza [Our World in Data](https://ourworldindata.org/renewable-energy) para construir sus series de energía renovable. Su archivo de Excel (101 hojas) se descargó del sitio del [Energy Institute](https://www.energyinst.org/statistical-review), y cada una de las tres hojas utilizadas se guardó como CSV. El PIB se descargó en CSV desde el [portal del Banco Mundial](https://datos.bancomundial.org/indicador/NY.GDP.PCAP.PP.CD).

Los archivos `_raw` se conservan tal como se descargaron, con encabezados, notas al pie y agregados regionales; toda la limpieza se realiza en el notebook.

### `mis_reportes/`

Contiene las páginas internas del sitio y los archivos que se muestran en ellas. Junto con `index.qmd`, Quarto usa estos archivos para construir el sitio publicado en [GitHub Pages](https://axeleduardoalvaradoarce.github.io/Proyecto_Equipo2/).

| Archivo | Tipo | Descripción |
|---|---|---|
| `bases_de_datos.qmd` | Página del sitio | Describe las fuentes utilizadas (Statistical Review of World Energy y Banco Mundial) y los archivos de datos del proyecto. Corresponde a la sección "Bases de datos" del menú. |
| `analisis.qmd` | Página del sitio | Presenta el notebook con el análisis completo, con enlaces para verlo en GitHub o abrirlo en Google Colab, e instrucciones para reproducirlo. Corresponde a la sección "Análisis" del menú. |
| `reporte.qmd` | Página del sitio | Muestra el reporte escrito en un visor y permite descargarlo en PDF. Corresponde a la sección "Reporte" del menú. |
| `Reporte_Transicion_Hacia_Energias_Renovables.pdf` | Documento | Reporte final del proyecto: problema, datos, limpieza, metodología, modelo, principales resultados, conclusiones, limitaciones y posibles extensiones. |
| `Dashboard_Energias_Renovables.html` | Visualización | Dashboard interactivo con los principales resultados del proyecto. Corresponde a la sección "Dashboard" del menú. |

Los archivos `.qmd` se convierten en páginas HTML al renderizar el sitio con `quarto render`, y el flujo de GitHub Actions lo hace automáticamente con cada cambio en la rama `main`. El PDF y el dashboard no se generan con Quarto, se copian tal cual al sitio porque están declarados en la sección `resources` de `_quarto.yml`.

## Reproducir el análisis

- **En Google Colab:** abre el notebook desde la sección [Análisis](https://axeleduardoalvaradoarce.github.io/Proyecto_Equipo2/mis_reportes/analisis.html) del sitio y ejecuta todas las celdas desde **Entorno de ejecución → Ejecutar todo**. No es necesario instalar nada.
- **En un entorno local:** clona este repositorio, instala las librerías y ejecuta el notebook con Jupyter:

    ```bash
    git clone https://github.com/AxelEduardoAlvaradoArce/Proyecto_Equipo2.git
    cd Proyecto_Equipo2
    pip install -r requirements.txt
    ```

El notebook descarga los datos desde GitHub, por lo que se requiere conexión a internet. La partición de los datos usa una semilla fija (`random_state=42`), así que los resultados son reproducibles. Las instrucciones detalladas están en la sección [Análisis](https://axeleduardoalvaradoarce.github.io/Proyecto_Equipo2/mis_reportes/analisis.html) del sitio.

## Equipo

- Aguilera Yáñez Mariana
- Alvarado Arce Axel Eduardo
- Canseco Galván Tanivet Leonor
- García Soto Kevin
- Hernández Mareles Francisco Javier
- Rendón Cardoso Karla
- Suárez Urbano David Hiram

## Ponentes del módulo

- Claudia Juárez
- Eduardo Selim

## Nota

En este proyecto se utilizó inteligencia artificial como herramienta auxiliar durante el desarrollo del trabajo, principalmente para apoyar en la revisión, organización y comprensión de información, así como en la resolución de dudas relacionadas con el proyecto. El contenido final fue revisado y validado por los integrantes del equipo, quienes son responsables de los resultados y conclusiones presentados.

---

*Diplomado Introducción Analítica a la Ciencia de Datos, Facultad de Ciencias, UNAM, 2026*
