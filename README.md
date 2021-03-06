# Flow Cytometry Data Analysis and Visualization Pipeline using flowDensity
* This repository consists of the pipeline scripts associated with the research paper “Implementing flowDensity for Automated Analysis of Bone Marrow Lymphocyte Population” by Eskandari et al. (2020).  
* The program analyzes flow cytometry data (.fcs) using flowDensity to automate analysis for evaluation of lymphocyte subsets in bone marrow biopsy specimens.  

* Outline:
![Screenshot](workflow.png)

## Usage:  

1. The main directory is divided into three groups - data, scripts, and result.
   * Data directory contains fcs files for different cell types such as T cells, B cells, and CD34 cells.
   User needs to manually add flow cytometry data in .fcs format for each cell type in data/{cell type}.
   * Result directory contains the output of the program in respective cell type folder.
    Sequential gating and PCA visualization outputs are present in result/{cell type}.
    Comprehensive expression analysis outputs are present in result/{cell type}/Independent/.  

2. The pipeline consists of the following four steps -
  * step 1: run flowDensity with optimized parameters with parental gating
  * step 2: run flowDensity with optimized parameters for comprehensive expression analysis
  * step 3: PCA visualization
  * step 4: Comprehensive expression analysis visualization

## Example
`[user@hpc scripts]$ bash runFlowDensityAnalysis.sh -t Tcells`  
`Started processing cell type ...Tcells`  
`Started processing sample ...Sample`  
`step 1: run flowDensity with optimized parameters with parental gating`  
`step 2: run flowDensity with optimized parameters for comprehensive expression analysis`  
`step 3: PCA visualization`  
`...processing PCA analysis...`  
`...cell type is ...Tcells`  
`...result files present in ../result/Tcells/`  
`step 4: Comprehensive expression analysis visualization`  
`...processing comprehensive expression analysis...`  
`...cell type is ...Tcells`  
`...result files present in ../result/Tcells/Independent/`  
`Completed processing sample ...Sample`  
`Completed processing cell type ...Tcells`  

* Result in ../result/Tcells/Independent/:
![Screenshot](result_output.PNG)
