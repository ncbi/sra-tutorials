# Search, Download, and Analyze SRA Data

In this module, we will walk through tools for working with public data from the Sequence Read Archive (SRA).

The goal is to show how you can move from finding relevant SRA records, to retrieving sequence data, to running a basic downstream analysis.


---


### 1. DuckDB

*Query SRA metadata -* We can use [DuckDB](https://duckdb.org/) to search and filter SRA metadata.

- Query SRA metadata
- Filter runs to identify accessions that may be useful downstream

### 2. SRA Toolkit 

*Download SRA data -* We can use the [SRA Toolkit](https://github.com/ncbi/sra-tools) to retrieve sequence data.

- Inspect an SRA accession
- Download SRA data
- Convert downloaded data into FASTQ files

### 3. SRA Taxonomy Analysis Tool

*Explore sample taxonomy -* We can use [STAT]((https://www.ncbi.nlm.nih.gov/sra/docs/sra-taxonomy-analysis-tool/)) to run a small taxonomy-based analysis.

- Use k-mer-based taxonomy info to summarize sequence content
- Scrub human data from a FASTQ file


---

### Conclusion 

Together, these modules act as a basic workflow for working with SRA data:

1. Find relevant records using SRA metadata  
2. Download selected data using the SRA Toolkit  
3. Analyze sequence content using a downstream tool like STAT  

By running through these exercises, you should have a better understanding of how these tools fit together and how they can support practical work with public sequencing data.