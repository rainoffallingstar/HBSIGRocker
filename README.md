# xcmsrocker

Rocker image for metabolomics data analysis

For Java, you could select [MSDK](https://msdk.github.io/).

For C/C++, you could select [openms](https://www.openms.de/) or [ProteoWizard](http://proteowizard.sourceforge.net/).

For C#, you could select [Prime](http://prime.psc.riken.jp/).

For Matlab, you could select [Bioinformatics Toolbox](https://www.nature.com/protocolexchange/protocols/4347#).

For python, you could select [emzed](http://emzed.ethz.ch/index.html).

However, I suggest this R-based image for starter and hopefully we could see a Julia platform in the future. 

Same software is not the end and detailed workflow would be the key to reproducible research in metabolomics studies. Xcmsrocker is a linux based docker image to simply the usage of R based metabolomics software. It includes multiple mainstream R packages used in metabolomics study with RStduio as IDE. Such image could be easy deployed on single machine or clusters on the go. To make the users do the right thing for metabolomics studies, rmwf package is attached in this image to provide detailed workflow template( File - New File - R Markdown - From Template - Select template with {rmwf}) from different research groups and facilitate the users to make metabolomics data analysis and/or comparison on the gaints' shoulder.

[![](https://images.microbadger.com/badges/image/yufree/xcmsrocker.svg)](https://microbadger.com/images/yufree/xcmsrocker "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/yufree/xcmsrocker.svg)](https://microbadger.com/images/yufree/xcmsrocker "Get your own version badge on microbadger.com")

## Usage

1. Install [Docker](https://www.docker.com/)

2. Pull the Rocker image `docker pull yufree/xcmsrocker:latest`

3. Use `docker run -e PASSWORD=xcmsrocker -p 8787:8787 yufree/xcmsrocker` to start the image

4. Open the browser and visit http://localhost:8787 or http://[your-ip-address]:8787 to power on RStudio server

5. Default user name is `rstudio` and password is `xcmsrocker`

6. Enjoy your data analysis!

## Packages

### Peak picking

- [xcms](https://bioconductor.org/packages/release/bioc/html/xcms.html) Generate peaks list/EIC/diffreport
- [apLCMS](https://sourceforge.net/projects/aplcms/) Generate peaks list
- [x13cms](http://pubs.acs.org/doi/10.1021/ac403384n) global tracking of isotopic labels in untargeted metabolomics

### Improved Peak picking

- [IPO](https://bioconductor.org/packages/release/bioc/html/IPO.html) For xcms peak picking optimazation
- [warpgroup](https://academic.oup.com/bioinformatics/article-lookup/doi/10.1093/bioinformatics/btv564) increase the precision for xcms peak picking and retention time correction
- [xMSanalyzer](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-14-15) improved Peak picking for xcms and apLCMS

#### For MS/MS

- [decoMS2](https://pubs.acs.org/doi/10.1021/ac400751j) An Untargeted Metabolomic Workflow to Improve Structural Characterization of Metabolites
- [msPurity](https://pubs.acs.org/doi/10.1021/acs.analchem.6b04358) Automated Evaluation of Precursor Ion Purity for Mass Spectrometry-Based Fragmentation in Metabolomics
- [MetaboDIA](https://pubs.acs.org/doi/10.1021/acs.analchem.6b05006) Quantitative metabolomics analysis using DIA-MS
- [MetDIA](http://www.metabolomics-shanghai.org/softwaredetail.php?id=40) Targeted Metabolite Extraction of Multiplexed MS/MS Spectra Generated by Data-Independent Acquisition for SWATH
- [SWATHtoMRM](http://www.metabolomics-shanghai.org/softwaredetail.php?id=128) Generating MRM transition from SWATH acquired data

### Peak filter/visulization/workflow

- [enviGCMS](https://cran.r-project.org/web/packages/enviGCMS/index.html) Filter peaks based on experimental design
- [metaMS](https://www.ncbi.nlm.nih.gov/pubmed/24656939)  An open-source pipeline for GC–MS-based untargeted metabolomics
- [ChemoSpec](https://cran.r-project.org/web/packages/ChemoSpec/index.html) Exploratory Chemometrics for Spectroscopy

### Peak annotation/group/selection

- [pmd](https://www.sciencedirect.com/science/article/pii/S0003267018313047) Select the independent peaks based on paired mass distance analysis
- [CAMERA](https://bioconductor.org/packages/release/bioc/html/CAMERA.html) Annotation of peaklists generated by xcms, rule based annotation of isotopes and adducts, isotope validation, EIC correlation based tagging of unknown adducts and fragments
- [RAMClustR](https://pubs.acs.org/doi/abs/10.1021/ac501530d) A feature clustering algorithm for non-targeted mass spectrometric metabolomics data
- [compMS2Miner](https://github.com/WMBEdmands/compMS2Miner) comprehensive and automatable annotation of metabolomic high-resolution LC-MS datasets
- [mz.unity](http://pubs.acs.org/doi/abs/10.1021/acs.analchem.6b01702) Defining and Detecting Complex Peak Relationships in Mass Spectral Data
- [Rdisop](https://bioconductor.org/packages/release/bioc/html/Rdisop.html) Decomposition of Isotopic Patterns
- [InterpretMSSpectrum](https://pubs.acs.org/doi/10.1021/acs.analchem.6b02743) Annotate and interpret deconvoluted mass spectra (mass*intensity pairs) from high resolution mass spectrometry devices
- [nontarget](https://cran.r-project.org/web/packages/nontarget/index.html) Detecting Isotope, Adduct and Homologue Relations in LC-MS Data

### Batch correction

- [Msprep](https://github.com/KechrisLab/MSPrep) Summarization, normalization and diagnostics for processing of mass spectrometry–based metabolomic data by Median, Quantile, Cross-Contribution Compensating Multiple Standard Normalization (CRMN), Surrogate Variable Analysis (SVA) and Removal of Unwanted Variation (RUV). 
- [BatchCorrMetabolomics](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4796354/) Improved batch correction in untargeted MS-based metabolomics by pool QC.

### Peaks identification

- [xMSannotator](http://pubs.acs.org/doi/abs/10.1021/acs.analchem.6b01214) MS1 annotation 
- [credential](http://pubs.acs.org/doi/abs/10.1021/ac503092d) A Platform to Benchmark and Optimize Untargeted Metabolomic Methods
- [MetFragr](http://ipb-halle.github.io/MetFrag/projects/metfragr/) The R package enables functionalities from the MetFrag Commandline tool to be used within the R programming language.

### Statistical analysis

- [MetMSLine](https://github.com/WMBEdmands/MetMSLine) R functions for automation of biomarker discovery based on processing downstream of peak picking softwares
- [MetaboAnalystR](https://github.com/xia-lab/MetaboAnalystR) R functions for MetaboAnalyst
- [caret](http://topepo.github.io/caret/index.html) general machine learning workflow for more than 200 models

### Chemometrics

- [rcdk](https://cran.r-project.org/web/packages/rcdk/index.html) Interface to the 'CDK' Libraries
- [ChemmineR](https://www.bioconductor.org/packages/devel/bioc/vignettes/ChemmineR/inst/doc/ChemmineR.html) Cheminformatics Toolkit for R 
- [webchem](https://github.com/ropensci/webchem) Chemical Information from the Web 

## Links

- [Use docker to package your metabolomics study](https://yufree.cn/en/2018/01/17/use-docker-to-package-your-metabolomics-study/)
- [Docker Hub](https://hub.docker.com/r/yufree/xcmsrocker/)
- [Docker tutorial](http://ropenscilabs.github.io/r-docker-tutorial/)
- [Rocker](https://www.rocker-project.org/)
- [Report extra metabolomics packages or issues](https://github.com/yufree/xcmsrocker/issues)
- [Meta-Workflow](https://bookdown.org/yufree/Metabolomics/)
