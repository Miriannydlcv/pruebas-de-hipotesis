---
editor_options:
  markdown:
    wrap: 72
output:
  html_document:
    df_print: paged
---

# **Análisis inferencial de reclamaciones y riesgo crediticio en el sistema bancario dominicano mediante pruebas t de Student**

### Descripción del proyecto

Este proyecto aplica pruebas t de Student para analizar diferencias en indicadores
clave del sistema bancario dominicano, específicamente en reclamaciones y riesgo crediticio.

Utilizando datos de la Superintendencia de Bancos (API) y el dataset UCI Credit Card, 
se evalúa si las diferencias observadas entre grupos responden a variabilidad 
aleatoria o a patrones estructurales estadísticamente significativos.

El análisis integra extracción de datos, limpieza, validación de supuestos, 
inferencia estadística y evaluación de relevancia práctica mediante tamaño del 
efecto.

### Objetivos:

 1. Comparar desempeño de reclamaciones (Popular vs sistema)
 2. Analizar relación entre límite de crédito y default
 3. Evaluar diferencias por tipo de producto
 4. Medir impacto post-pandemia


### **Tecnologías utilizadas**

-   R / RStudio

-   knitr + rmarkdown

-   ggplot2

-   LaTeX (para renderizado del informe PDF)

-   Archivo *preamble.tex* para formato profesional

-   Variables de entorno *(.Renviron)* para la API key

### **Estructura del repositorio**

/02_Pruebas_T/

│── Pruebas_T.Rmd                 \# informe principal

│── Anexo.Pruebas_T.Rmd           \# anexo técnico con el código completo

│── Informe_final_Pruebas_T.pdf   \# reporte final en PDF

│── Anexo.Pruebas_T.pdf           \# anexo técnico con el código completo en PDF

│── UCI_Credit_Card.CSV           \# Dataset para caso 2.1, de muestras ind.

│── preamble.tex                  \# configuración LaTeX

│── Renv.R                        \#Archivo para gestionar dependencias reproducibles en R

│── README_T.md

│── /figures/                     \# gráficos exportados


### **Autenticación con la API *(colocar en .Renviron)***

Antes de reproducir el análisis, agregar:

`API_KEY_SB=tu_api_key_aqui`

### **Reproducibilidad**

Las muestras son generadas mediante:

`set.seed(123)`

Esto garantiza que cualquier persona que ejecute el análisis obtenga
exactamente los mismos resultados, siempre que utilice los mismos
periodos y parámetros de consulta.

### **Resultados principales**

**Prueba T de una muestra**
Desempeño significativamente inferior de Banco Popular frente al sistema.
t = -145.49, gl = 38, p < 0.001, d = -23.3

**Prueba T de muestras independientes — Caso 2.1 (Default)**
El límite de crédito discrimina riesgo de default de forma moderada.
t = 2.63, gl = 126, p = 0.0095, d = 0.62

**Prueba T de muestras independientes — Caso 2.2 (Productos)**
Existe una brecha estructural entre productos crediticios y transaccionales.
t = 8.19, gl = 76, p < 0.001, d = 1.85

**Prueba T de muestras relacionadas (Post-pandemia)**
No se evidencia un cambio significativo tras la pandemia.
t = -0.30, gl = 14, p = 0.77, d = 0.08

### **Reproducción del informe**

`rmarkdown::render("02_Pruebas_T.Rmd")`

### Lecciones aprendidas

 - Las diferencias en indicadores bancarios pueden ser estructurales y no 
producto del azar.

 - La significancia estadística depende del tipo de contraste planteado.

 - No todos los cambios operativos generan mejoras medibles.
 
 - El tamaño del efecto es clave para interpretar relevancia práctica.
 -  Las pruebas t son robustas incluso cuando los supuestos no se cumplen en su 
 totalidad.

### **Autora**

Mirianny De La Cruz Ventura

Análisis de Datos & BI

