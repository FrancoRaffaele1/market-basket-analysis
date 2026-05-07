# 🛒 Análisis de la Cesta de la Compra y Sistema de Recomendación para E-commerce

**Universidad Internacional de La Rioja (UNIR)**  
**Máster Universitario en Big Data y Ciencia de Datos — Trabajo Final de Máster**

---

## 📋 Descripción del proyecto

Este repositorio contiene la implementación completa de un **sistema de recomendación de productos para e-commerce** basado en análisis de la cesta de la compra mediante algoritmos de reglas de asociación (Apriori y FP-Growth), aplicado sobre el dataset UCI Online Retail con más de 500.000 transacciones reales.

El proyecto sigue un pipeline de seis fases alineado con la metodología **CRISP-DM**, cubriendo el preprocesamiento de datos, análisis exploratorio, entrenamiento del modelo, comparativa de algoritmos, desarrollo del motor de recomendación y simulación del impacto en el negocio.

---

## 👥 Autores

| Nombre | Rol |
|--------|-----|
| Franco Adrián Raffaele | Autor |
| Lucía Pérez Aída | Autora |
| Saioa Cuadrado Recio | Autora |
| Igor Pascual Sagastagotia | Tutor |

**Fecha:** Junio 2026

---

## 🎯 Objetivos

El objetivo principal es diseñar, implementar y evaluar un sistema de recomendación capaz de identificar patrones de co-compra estadísticamente significativos en datos transaccionales reales y traducirlos en estrategias de venta cruzada accionables, estimando mediante simulación su impacto potencial en el valor medio del carrito (AOV).

### Resumen de objetivos SMART

| # | Objetivo | Meta | Resultado |
|---|----------|------|-----------|
| OE1 | Reducción de ruido en los datos | ≥ 20% | 26,6% ✅ |
| OE2 | EDA: productos, geografía, estacionalidad | Completo | ✅ |
| OE3 | Reglas de asociación con lift ≥ 1,5 | > 0 reglas | 312 reglas ✅ |
| OE4 | FP-Growth produce resultados equivalentes | Mismas reglas | ✅ |
| OE5 | FP-Growth más rápido que Apriori | Más rápido | ~77% más rápido ✅ |
| OE6 | Confianza media > 40% | > 40% | ✅ |
| OE7 | Incremento AOV entre 10% y 25% | 10–25% | +13,4% / +21,8% ✅ |
| OE8 | Justificación estratégica completa | Completo | ✅ |

---

## 🗂️ Estructura del repositorio

```
market-basket-analysis/
│
├── 📓 market_basket_analysis_FINAL.ipynb   ← Notebook principal (pipeline completo)
├── 📄 requirements.txt                      ← Dependencias Python
├── 📄 README.md                             ← Este fichero
│
├── 📂 outputs/                              ← Exportaciones CSV para dashboard Power BI
│   ├── rules_apriori.csv
│   ├── rules_fpgrowth.csv
│   ├── comparison_algorithms.csv
│   ├── recommendations_examples.csv
│   └── aov_simulation.csv
│
└── 📂 figures/                              ← Gráficos y visualizaciones generados
    ├── fig2_paises.png
    ├── fig3_productos.png
    ├── fig4_temporal.png
    ├── fig5_productos_factura.png
    ├── fig6_scatter_apriori.png
    ├── fig7_scatter_fpgrowth.png
    ├── fig8_comparativa.png
    └── fig9_aov_simulacion.png
```

---

## 📦 Dataset

**UCI Online Retail Dataset**
- **Fuente:** https://archive.ics.uci.edu/dataset/352/online+retail
- **Referencia APA:** Chen, D. (2015). *Online Retail* [Conjunto de datos]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
- **Descripción:** 541.909 transacciones de una empresa minorista del Reino Unido (2010–2011)
- **Formato:** Excel (.xlsx)

> ⚠️ El dataset no está incluido en este repositorio. Descárgalo desde el enlace anterior y colócalo dentro de la carpeta `data/` antes de ejecutar el notebook.

---

## 🛠️ Stack tecnológico

| Tecnología | Uso |
|------------|-----|
| Python 3.11 | Lenguaje base |
| pandas | Manipulación y preprocesamiento de datos |
| numpy | Operaciones numéricas y simulación del AOV |
| mlxtend | Implementación de Apriori y FP-Growth |
| matplotlib / seaborn | Visualización de resultados |
| Jupyter Notebook | Entorno de desarrollo |
| Power BI | Dashboard interactivo de negocio |

---

## ⚙️ Instalación y ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/FrancoRaffaele1/market-basket-analysis.git
cd market-basket-analysis
```

### 2. Crear entorno virtual
```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac / Linux
```

### 3. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 4. Descargar el dataset
Descargar `Online Retail.xlsx` desde el enlace UCI indicado arriba y colocarlo dentro de la carpeta `data/`.

### 5. Ejecutar el notebook
```bash
jupyter notebook market_basket_analysis_FINAL.ipynb
```

Ejecutar todas las celdas con **Kernel → Restart & Run All**.

---

## 📊 Pipeline del análisis

```
Datos brutos (541.909 registros)
        │
        ▼
[Fase 1] Carga e inspección del dataset
        │
        ▼
[Fase 2] Preprocesamiento y limpieza  →  Reducción de ruido del 26,6% (OE1 ✅)
        │
        ▼
[Fase 3] Análisis exploratorio (EDA)  →  Top productos, geografía, estacionalidad (OE2 ✅)
        │
        ▼
[Fase 4] Modelado: Apriori + FP-Growth  →  312 reglas de alta calidad (OE3–OE5 ✅)
        │
        ▼
[Fase 5] Motor de recomendación  →  Hasta 5 sugerencias por cesta (OE6 ✅)
        │
        ▼
[Fase 6] Simulación de impacto AOV  →  Incremento estimado del 13,4% al 21,8% (OE7–OE8 ✅)
```

---

## 🔑 Resultados principales

- **312 reglas de alta calidad** (lift ≥ 1,5, confianza media > 40%)
- **FP-Growth un 77% más rápido** que Apriori con resultados idénticos
- **Incremento estimado del AOV** del 13,4% (adopción 10%) al 21,8% (adopción 20%)
- Motor de recomendación con sugerencias **interpretables y accionables** comercialmente
- Resultados exportados como **ficheros CSV** para dashboard interactivo en Power BI

---

## 📚 Referencias principales

- Agrawal, R., & Srikant, R. (1994). Fast algorithms for mining association rules. *VLDB*, 487–499.
- Han, J., Pei, J., & Yin, Y. (2000). Mining frequent patterns without candidate generation. *ACM SIGMOD*, 1–12.
- Chen, D. (2015). *Online Retail* [Conjunto de datos]. UCI Machine Learning Repository.
- Zaki, M. J., & Meira, W. (2020). *Data mining and machine learning* (2.ª ed.). Cambridge University Press.

---

## 📄 Licencia

Este repositorio se publica con fines académicos en el marco del Trabajo Final de Máster de la Universidad Internacional de La Rioja (UNIR). El dataset UCI Online Retail está disponible bajo licencia pública del UCI Machine Learning Repository.
