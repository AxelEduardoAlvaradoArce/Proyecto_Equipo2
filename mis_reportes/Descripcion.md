# mis_reportes

Esta carpeta contiene las páginas internas del sitio de nuestro proyecto y los archivos que se muestran en ellas. Junto con `index.qmd`, Quarto usa estos archivos para construir el sitio publicado en [GitHub Pages](https://axeleduardoalvaradoarce.github.io/Proyecto_Equipo2/).

## Contenido

| Archivo | Tipo | Descripción |
|---|---|---|
| `bases_de_datos.qmd` | Página del sitio | Describe las fuentes utilizadas (Statistical Review of World Energy y Banco Mundial) y los archivos de datos del proyecto, Se abre desde la sección "Bases de datos" del menú. |
| `analisis.qmd` | Página del sitio | Presenta el notebook con el análisis completo, con enlaces para verlo en GitHub o abrirlo en Google Colab, e instrucciones para reproducirlo. Se abre desde la sección "Análisis" del menú. |
| `reporte.qmd` | Página del sitio | Muestra el reporte escrito en un visor y permite descargarlo en PDF. Se abre desde la sección "Reporte" del menú. |
| `Reporte_Transicion_Hacia_Energias_Renovables.pdf` | Documento | Reporte final del proyecto: problema, datos, limpieza, metodología, modelo, principales resultados, conclusiones, limitaciones y posibles extensiones.|
| `Dashboard_Energias_Renovables.html` | Visualización | Dashboard interactivo con los principales resultados del proyecto. Se abre desde la sección "Dashboard" del menú. |

## Notas

- Los archivos `.qmd` se convierten en páginas HTML al renderizar el sitio con `quarto render`; el flujo de GitHub Actions lo hace automáticamente con cada cambio en la rama `main`.
- El PDF y el dashboard no se generan con Quarto, ya que se copian tal cual al sitio porque están declarados en la sección `resources` de `_quarto.yml`.
