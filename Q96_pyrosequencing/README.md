# Q96 Pyrosequencing Analysis

Targeted bisulfite pyrosequencing provides accurate measurements of DNA methylation for CpG sites in small (~60-140 bp) regions of the genome. These estimates are made by looking at the relative fluorescent intensity of C's to T's at each CpG and provided as a beta value by the Pyromark software. 

Generally, the greatest source of technical variability in pyrosequencing data comes from slight differences in these ratios introduced during PCR amplification prior to sequencing. To address this, I developed a pipeline and custom functions in R that import the raw data provided by the pyrosequencer and check for variation across triplicate reactions that exceeds 5% (the estimated detection sensitivity of the Q96 sequencing platform). 

## Description of Contents
- [sample_QC.rmd](https://github.com/stephen-siecinski/SOARS-B/blob/main/Q96_pyrosequencing/sample_QC.rmd)
  -  Import, clean, and concatenate machine output files. Flag samples with excessive technical variability across triplicate measures (>5%), generate summary statistics for samples that passed QC, export tables of passed samples and samples that need to be rerun. 
- [Q96 Analysis.rmd](https://github.com/stephen-siecinski/SOARS-B/blob/main/Q96_pyrosequencing/Q96_analysis.rmd)
  - Import post-QC Q96 methylation and SOARS-B participant data, analyze using base R linear modeling, generate summary plots.
- [Q96_rerun_checks.rmd](https://github.com/stephen-siecinski/SOARS-B/blob/main/Q96_pyrosequencing/Q96_rerun_checks.rmd)
  -  Used to manage samples in coordination with robotic sorting and visual inspection to identify depleted samples that needed to be reallocated.

#### Summary results - Post-QC Q96 pyrosequencing data averaged across three CpG sites by batch
<img src="https://github.com/stephen-siecinski/SOARS-B/blob/main/Q96_pyrosequencing/pyrosequencing_batch_average_meth_20210223.png" width=1000>
