# TFM_Aarón_Marcén
Repositorio en el que se adjuntan los scripts de R-Markdown y los informes HTML de mi TFM. Además de todos los archivos necesarios para generar los análisis y los archivos de resultados.

Para el desarrollo de este trabajo final de máster llamado **Análisis Transcriptómico del DLBCL con afectación al sistema nervioso central**, se han generado 3 workflows:
- El primero con el tratamiento de los datos y el control de calidad, llamado: **Tratamiento_datos_QC**.
- El segundo con el análisis de expresión diferencial, llamado: **Análisis_DESeq2**.
- Y el tercero con el análisis de deconvolución del tumor microenviroment, llamado: **Immunedeconv**.

Cada uno de ellos tiene asociado su script en formato R-Markdown (documento que intercala texto plano con chunks de código) y el informe resultado de renderizar el script, en formato HTML.

Para poder ejecutar los scripts, se adjuntan los archivos de datos de entrada utilizados:
- **HTG Transcriptome database.xlsx**: archivo Excel que contiene la matriz de counts de la base de datos original. 
- **HTG Transcriptome metadata.xlsx**: archivo Excel que contiene la matriz de metadatos de la base de datos original. 
- **counts.xlsx**: archivo Excel que contiene la matriz de counts, modificada durante el workflow *Tratamiento_datos_QC*. 
- **meta.xlsx**: archivo Excel que contiene la matriz de metadatos, modificada durante el workflow *Tratamiento_datos_QC*.

Los archivos originales se importan en el primer script **Tratamiento_datos_QC**, mientras que los archivos modificados son los utilizados en el segundo **Análisis_DESeq2** y tercer script **Immunedeconv**. 

Y los archivos de salida, necesarios para emular los análisis realizados en el servidor web de CIBERSORT y en el programa GSEA:
- **tpm_counts.csv**: Archivo csv con la matriz de counts de los genes prefiltrados y normalizados mediante la normalización TPM. Archivo de entrada para el servidor web de CIBERSORTx.
- **CIBERSORTx_Results.csv**: Archivo csv con la matriz de resultados obtenida de la ejecución de CIBERSORTx abs, en su servidor web. Necesario para generar los gráficos de CIBERSORTx abs en el script *Immunedeconv*.
- **ncounts_GSEA.csv** Archivo csv con la matriz de counts de los genes prefiltrados y normalizados mediante la normalización de DESeq2. Archivo utilizado en los análisis con GSEA.

También se incluyen los archivos de resultados generados en los scripts:
- Análisis de expresión diferencial, comparación PCNSL vs SCNSL: 
  - **full_genes_PCNSLvsSCNSL.csv**: Archivo csv con los resultados  para todos los genes prefiltrados. 
  - **genes_PCNSLvsSCNSL.csv**: Archivo csv con los resultados de los genes con adj.p-value < 0.05 & LFC > 1.
  - **genes_PCNSLvsSCNSL2.csv**: Archivo csv con los resultados de los genes con adj.p-value < 0.1 & baseMean > 100.
    
- Análisis de expresión diferencial, comparación DLBCL with CNS inv vs DLBCL wo CNS inv: 
  - **full_genes_DLBCL_withvswo.csv**: Archivo csv con los resultados del análisis diferencial para todos los genes prefiltrados. 
  - **genes_DLBCL_withvswo.csv**: Archivo csv con los resultados de los genes con adj.p-value < 0.05 & LFC > 1.
  - **genes_DLBCL_withvswo2.csv**: Archivo csv con los resultados de los genes con adj.p-value < 0.1 & baseMean > 100.

- Análisis de deconvolución del TME:
  - **imm_epic.csv**: Archivo csv con la matriz de resultados obtenida de immunedeconv con el método EPIC.
  - **imm_qti.csv**: Archivo csv con la matriz de resultados obtenida de immunedeconv con el método quanTIseq.
  - **imm_xcell.csv**: Archivo csv con la matriz de resultados obtenida de immunedeconv con el método xCell.

