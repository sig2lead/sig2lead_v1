# sig2lead_v1
Sig2Lead aims to facilitate drug discovery and re-purposing by connecting small molecule and target gene knock-down (KD) transcriptional signatures generated by the LINCS consortium, in conjunction with cheminformatics approaches. 

For a target gene specified by the user, putative inhibitors are identified as those drug-like molecules in LINCS that have signatures concordant with a KD signature of the target. Note that LINCS arguably represents the largest resource for pharmacogenomics to date, with over 20,000 small molecules and about 5,000 gene KDs transcriptionally profiled, thus covering a large subset of the drug-like chemical space and druggable subset of the genome.  

Furthermore, if a set of candidate molecules is provided, e.g., identified by virtual or experimental screening, these external candidate molecules are ranked based on their chemical similarity to ‘concordant’ LINCS analogs using a fast chemical similarity search. Additionally, Sig2Lead can be used to prepare input files for docking simulations to be performed in conjunction with connectivity-based analysis to improve the specificity (see https://www.biorxiv.org/content/10.1101/2020.11.25.399238v1.full), as well as identify LINCS analogs irrespective of their connectivity to a target of interest.

Installation/Configuration of Sig2Lead_v1

Sig2Lead is available as a stand alone R Shiny app that requires RStudio to run and as a docker container.  The RStudio version can simply be downloaded from Github while the dockerized version is available on Docker Hub.  The RStudio version requires that R and RStudio be locally installed on the user’s computer and requires the installation of all requisite R packages.  The dockerized version simply requires a web browser to run the app and does not require local installation/configuration of R, RStudio, or R packages.  This manual provides instructions for both versions.  

Installation/Configuration of RStudio Version

A.  Install R and RStudio

The latest version of R is required for configuration of Sig2Lead. At the time of writing this manual, that was version 4.0.3. This version can be downloaded at:
	http://www.r-project.org/

Additionally, RStudio is needed and can be downloaded at:
	https://www.rstudio.com/products/rstudio/download/

B.  Download Sig2Lead from Github

Sig2Lead and associated files can be downloaded from:
https://github.com/sig2lead/sig2lead_v1/

C.  Install Required Packages/Libraries

Once R and RStudio are installed, R Shiny must be installed. This can be completed by typing into the R console:

install.packages(“shiny”)

All other dependencies and libraries will be installed upon the first time running the application.
        This step may not be handled properly on MacOS, requiring a step by step installation of missing libraries. An alternative for Mac users is to use the dockerized version that takes care of all the dependencies.
        To run the application, click the Run App button at the top middle of the RStudio interface.
