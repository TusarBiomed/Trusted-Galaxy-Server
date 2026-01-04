# Galaxy Open vs. Trusted Server Performance Benchmark

This repository contains a Jupyter Notebook for benchmarking the performance of **Galaxy workflows** between **Open Server** and **Trusted Server** configurations. The notebook automates the execution of multiple bioinformatics workflows and collects runtime metrics for comparative analysis.

## 🧬 Workflows Benchmarked

The following Galaxy workflows are evaluated:

1. **Transcriptomics RNA-Seq Counts to Genes**
   - Processes RNA-Seq count data into gene-level expressions.
2. **GO Enrichment Analysis**
   - Performs Gene Ontology enrichment analysis on gene lists.
3. **Single Cell QC with scater**
   - Quality control workflow for single-cell RNA-Seq data.
4. **Formation of Super Structures on Xi**
   - Epigenomics workflow for chromatin structure analysis.

## 🛠️ Technologies Used

- **bioblend**: Python library for Galaxy API interaction.
- **requests**: For making HTTP requests to Galaxy job endpoints.
- **matplotlib**: For plotting runtime comparisons.
- **Galaxy Instances**: Both open and trusted server instances.

## 📁 Notebook Structure

The notebook is organized into sections:

1. **Setup and Imports**  
   - Imports necessary libraries and sets up Galaxy instances.

2. **Workflow Invocation**  
   - Loops through each workflow, locates input data, and invokes workflows repeatedly to generate runtime data.

3. **Job Metrics Collection**  
   - Collects job execution times from Galaxy’s job API.

4. **Data Aggregation**  
   - Aggregates per-job times into per-history totals.

5. **Visualization**  
   - Compares runtime performance between open and trusted servers using line plots.

## 📊 Output

The notebook generates four comparison plots:

- `RNA.png`: RNA-Seq workflow runtime comparison.
- `GO.png`: GO enrichment workflow runtime comparison.
- `scqc.png`: Single-cell QC workflow runtime comparison.
- `s_str.png`: Super Structure formation workflow runtime comparison.

Each plot shows runtime (in seconds) vs. number of histories for both server types.

## 📈 Purpose
This benchmarking helps understand the performance overhead (if any) when running workflows in a trusted vs. open Galaxy environment, which is useful for system administrators and researchers optimizing their Galaxy deployments.
