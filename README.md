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

## Cómo reproducir el análisis

1. Abre el notebook `Proyecto_Energias_Analisis.ipynb` en Google Colab o en un entorno local con Jupyter.
2. Instala las librerías necesarias:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn plotly
   ```
3. Ejecuta el notebook de principio a fin (Entorno de ejecución + Ejecutar todo). El notebook descarga los datos crudos directamente desde este repositorio, los limpia, construye la base consolidada y ajusta los modelos.

## Entregables

- **Reporte** del proyecto (documento con problema, metodología, modelo, resultados y conclusiones).
- **Dashboard** interactivo con los principales resultados.
- **Sitio web** que reúne todo lo anterior.

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

---

*Diplomado Introducción Analítica a la Ciencia de Datos, Facultad de Ciencias, UNAM, 2026*
