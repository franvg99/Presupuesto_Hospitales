# 🏥 Análisis de Presupuesto Hospitalario - GCBA (2025)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458)
![Power BI](https://img.shields.io/badge/Tools-Power%20BI-F2C811)
![Status](https://img.shields.io/badge/Status-Completado-green)

## 📌 Descripción del Proyecto

Este proyecto consiste en un pipeline de **Ingeniería y Análisis de Datos** enfocado en la ejecución presupuestaria de los hospitales públicos de la Ciudad Autónoma de Buenos Aires (GCBA). 

El objetivo principal es transformar datos abiertos crudos y dispersos en un modelo de inteligencia de negocios (BI) robusto, permitiendo visualizar métricas clave sobre la asignación y el uso de los recursos financieros en el sistema de salud pública.

El flujo de trabajo abarca desde la extracción y limpieza de datos con **Python (Pandas)**, pasando por el modelado dimensional (Esquema de Estrella), hasta la visualización interactiva en **Power BI**.

---

## ⚙️ Arquitectura del Pipeline

El proyecto sigue un flujo de trabajo ETL (Extract, Transform, Load) clásico:

1.  **Extracción (Extract):**
    * Ingesta de datos crudos desde el portal de Datos Abiertos del GCBA (formato Excel).
    * Dataset original: Presupuesto ejecutado del primer trimestre 2025.

2.  **Transformación (Transform) - *Jupyter Notebook*:**
    * Limpieza de datos y selección de columnas relevantes.
    * **Filtrado de dominio:** Aislamiento de las Unidades Ejecutoras correspondientes a "Hospitales".
    * **Normalización:** Creación de tablas de dimensiones para eliminar redundancias.
    * **Modelado:** Generación de un **Esquema de Estrella (Star Schema)** con las siguientes tablas:
        * `dim_hospitales`: Catálogo de instituciones.
        * `dim_ubicaciones`: Relación geográfica (Comunas).
        * `dim_actividades`: Actividades presupuestarias normalizadas.
        * `dim_clasificadores`: Jerarquía de Inciso, Principal y Partida.
        * `fact_presupuesto`: Tabla central con métricas financieras (Sancionado, Vigente, Devengado).

3.  **Carga y Visualización (Load & Viz) - *Power BI*:**
    * Importación del modelo relacional.
    * Creación de medidas DAX para KPIs (`% de Ejecución`, `Desvío Presupuestario`).
    * Desarrollo de Dashboard interactivo con mapas coropléticos y análisis por categorías.

---

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python 3
* **Librerías:** * `pandas`: Manipulación de DataFrames y lógica ETL.
    * `numpy`: Operaciones numéricas.
* **Visualización:** Microsoft Power BI.
* **Formato de Datos:** Excel (.xlsx), Jupyter Notebook (.ipynb).

---

## 📊 Estructura del Repositorio

```text
├── data/
│   ├── raw/                  # Dataset original del GCBA
│   └── processed/            # Archivo transformado listo para Power BI (presupuesto_hospitales.xlsx)
├── notebooks/
│   └── PRESUPUESTO_HOSPITALES.ipynb  # Script principal de ETL
├── reports/
│   └── Presupuestos_Hospitalarios.pbix # Archivo de Power BI
├── images/                   # Capturas del dashboard (opcional)
└── README.md                 # Documentación del proyecto
