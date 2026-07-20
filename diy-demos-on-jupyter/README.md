# Search, Download, and Analyze SRA Data

These Jupyter-based demos introduce tools for working with public data from the Sequence Read Archive (SRA).

The core workflow shows how to move from finding relevant SRA records, to retrieving sequence data, to performing a basic downstream analysis.

A fourth, complementary demo shows how to retrieve gene-centered information using NCBI GeneIDs.

> **Note**
> These exercises are provided as `.ipynb` notebooks and are designed for a Jupyter environment. The commands and examples can also be adapted for scripts or run directly in a terminal.

By completing these exercises, you should have a better understanding of how these tools fit together and how they can support practical work with public sequencing data.

---

## Demos

### 1. DuckDB

Use [DuckDB](https://duckdb.org/) to search and filter large SRA metadata files with SQL in order to reduce memory use, data movement, and compute cost.

- Query SRA metadata using SQL
- Select only the columns needed for an analysis
- Filter records before loading results into memory
- Identify SRA run accessions for downstream analysis

### 2. SRA Toolkit

Download SRA data using the [SRA Toolkit](https://github.com/ncbi/sra-tools) to retrieve sequence data.

- Inspect an SRA accession
- Download SRA data
- Convert downloaded data into FASTQ files

### 3. SRA Taxonomy Analysis Tool

Explore sample taxonomy using the [SRA Taxonomy Analysis Tool (STAT)](https://www.ncbi.nlm.nih.gov/sra/docs/sra-taxonomy-analysis-tool/) to perform a small taxonomy-based analysis.

- Summarize sequence content using k-mer-based taxonomic information
- Screen for and remove human reads from a FASTQ file

### 4. NCBI Gene and GeneID

Retrieve gene-centered information using [NCBI Gene](https://www.ncbi.nlm.nih.gov/datasets/gene/) and NCBI GeneIDs to look up gene records and retrieve related metadata and sequence information.

- Find genes by symbol, GeneID, or RefSeq accession
- Review gene metadata and associated transcript or protein accessions
- Retrieve gene-centered records for reference or follow-up analysis

---
