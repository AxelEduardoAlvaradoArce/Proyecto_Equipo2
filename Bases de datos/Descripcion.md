## Contenido

Esta carpeta contiene las bases de datos utilizadas para el desarrollo del proyecto. A continuación, se describe el contenido de cada archivo, así como las fuentes de las que se obtuvieron los datos.

| Archivo | Descripción |
|---|---|
| `Proyecto_Transicion_Hacia_Energias_Renovables.ipynb` | Notebook con el análisis completo: obtención y limpieza de los datos, análisis exploratorio, cálculo de la penetración renovable y de la velocidad de transición, modelos Lasso y Ridge, diagnóstico y proyección a 2035. |
| `tes_per_capita_raw.csv` | Suministro total de energía por habitante, en gigajoules (GJ). |
| `renovables_excl_hidro_raw.csv` | Generación de electricidad con fuentes renovables, excluyendo la hidroeléctrica, en teravatios-hora (TWh). |
| `generacion_electrica_raw.csv` | Generación total de electricidad, en teravatios-hora (TWh). |
| `pib_per_capita_ppp_raw.csv` | PIB per cápita en paridad de poder adquisitivo (PPA), en dólares internacionales corrientes. |
| `datos.csv` | Base de datos final, obtenida tras limpiar e integrar las cuatro fuentes, con una observación por país y año. |

## Fuentes de datos

| Archivo | Fuente |
|---|---|
| `tes_per_capita_raw.csv` | Energy Institute, Statistical Review of World Energy (hoja "TES per capita") |
| `renovables_excl_hidro_raw.csv` | Energy Institute, Statistical Review of World Energy (hoja "Ren power (excl hydro) - TWh") |
| `generacion_electrica_raw.csv` | Energy Institute, Statistical Review of World Energy (hoja "Electricity Generation - TWh") |
| `pib_per_capita_ppp_raw.csv` | Banco Mundial, Indicadores del Desarrollo Mundial (indicador NY.GDP.PCAP.PP.CD) |

El Statistical Review of World Energy es la fuente que utiliza [Our World in Data](https://ourworldindata.org/renewable-energy) para construir sus series de energía renovable. Su archivo de Excel (101 hojas) se descargó del sitio del [Energy Institute](https://www.energyinst.org/statistical-review) y cada una de las tres hojas utilizadas se guardó como CSV. El PIB se descargó en CSV desde el [portal del Banco Mundial](https://datos.bancomundial.org/indicador/NY.GDP.PCAP.PP.CD).

Los archivos `_raw` se conservan tal como se descargaron, con encabezados, notas al pie y agregados regionales; toda la limpieza se realiza en el notebook.

