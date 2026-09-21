# Fusarium oxysporum 3RR — Genome Analysis Pipeline

Bioinformatics pipeline supporting:
Nebli S, Saadaoui O, Gargouri H, Abid C, Jardak M, Djebali F, Loukil S, Marzoug RB, Jlaiel L, Croze S, Lachuer J, Kharrat N and Mnif S (2026) The endophyte Fusarium oxysporum 3RR genome analysis identifies bioactive compounds targeting biofilm formation. Front. Microbiol. 17:1841716. doi: 10.3389/fmicb.2026.1841716

## Data Availability
Raw sequencing data: NCBI BioProject [PRJNA1444486](https://www.ncbi.nlm.nih.gov/bioproject/1444486)

## Workflow Adaptation
Parts of the bioinformatics workflow were based on the protocol described in the Nexomis Eukaryotic de novo Genome Tutorial (https://nexomis.github.io/tuto-euk-de-novo-genome/). The original pipeline was modified and optimized for the present dataset and analytical objectives.

## Pipeline Overview
| Step | Notebook | Description |
|------|----------|-------------|
| 1 | 01_primary_analysis | QC, trimming, Kraken2 classification |
| 2 | 02_kmer_analysis | Genome size estimation with KAT |
| 3 | 03_hybrid_assembly | SPAdes hybrid assembly |
| 4 | 04_assembly_quality | QUAST + BUSCO evaluation |
| 5 | 05_secondary_scaffolding | Ragout + Cactus scaffolding |
| 6 | 06_repeat_masking | RepeatModeler + RepeatMasker |
| 7 | 07_gene_prediction | BRAKER3 gene prediction |
| 8 | 08_functional_annotation | InterProScan + eggNOG + PHI-base |
| 9 | 09_comparative_genomics | PHAST + OrthoFinder |

## Requirements
All tools are run via Apptainer containers. See `environment/dependencies.md`.

## Usage
Clone and set your working directory:
```bash
git clone https://github.com/SyrineNebli/fusarium-3RR-genome.git
cd fusarium-oxysporum-3RR-genome
```
Then run notebooks in order.
