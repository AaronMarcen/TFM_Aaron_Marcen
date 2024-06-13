# TFM_Aarón_Marcén
Repositorio en el que se adjuntan los scripts de R-Markdown y los informes HTML de mi TFM.

Para el desarrollo de este trabajo final de máster llamado Análisis Transcriptómico del DLBCL con afectación al sistema nervioso central, se han generado 3 workflows:
- El primero con el tratamiento de los datos y el control de calidad, llamado: **Tratamiento_datos_QC**
- El segundo con el análisis de expresión diferencial, llamado: **Análisis_DESeq2**
- Y el tercero con el análisis de deconvolución del tumor microenviroment, llamado: **Immunedeconv**

Cada uno de ellos tiene asociado su script en formato R-Markdown (documento que intercala texto plano con chunks de código) y el informe resultado de renderizar el script, en formato HTML.

Para poder ejecutar los scripts, también se adjuntan los archivos de datos de entrada utilizados:
- **HTG Transcriptome database.xlsx**: archivo Excel que contiene la matriz de counts de la base de datos original. 
- **HTG Transcriptome metadata.xlsx**: archivo Excel que contiene la matriz de metadatos de la base de datos original. 
- **counts.xlsx**: archivo Excel que contiene la matriz de counts, modificada durante el workflow *Tratamiento_datos_QC*. 
- **meta.xlsx**: archivo Excel que contiene la matriz de metadatos, modificada durante el workflow *Tratamiento_datos_QC*.

Los archivos originales se importan en el primer script **Tratamiento_datos_QC**, mientras que los archivos modificados son los utilizados en el segundo **Análisis_DESeq2** y tercer script **Immunedeconv**. 
