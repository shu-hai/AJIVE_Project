# AJIVE_Project

This repository provides the AJIVE software in Matlab and all related Matlab scripts to reproduce the results in the paper 
[**Angle-basied Joint And Individual Variation Explained**](https://arxiv.org/pdf/1704.02060.pdf) (Feng et.al., 2017). 

## Organization

The folder, *AJIVECode*, provides the self-contained scripts to implement the AJIVE algorithm, which should be added to the Matlab search path to run the AJIVE software. The script *AJIVEtest.m* provides unit testing for the AJIVE software. The folder  *DataExample* contains the input toy dataset shown in Figure 2 of the paper, the TCGA dataset studied in Section 3.1 and the mortality dataset in Section 3.2 of the paper. The folders *TCGA* and *Mortality* contain the scripts to reproduce the corresponding figures for these two datasets in the paper. In order to utilize these scripts to reproduce the plots in the paper, [*Marron’s Matlab Software*](http://marron.web.unc.edu/sample-page/marrons-matlab-software/) needs to be installed.

## Toy Example

Please run the script *AJIVEdemo.m* for illustration of the application of the AJIVE algorithm to the toy example. This toy example has two data blocks, X (100 × 100) and Y (10000 × 100), with patterns corresponding to joint and individual structures. The data has been simulated so expected row means are 0. Each column of these matrices is regarded as a common data object and each row is considered as one feature.  This toy example has one joint component, one individual X component, and two individual Y components. 

## Example of Application 1: TCGA data set

The script *TCGA/TCGA_AJIVE_Analysis.m* runs our AJIVE analysis of the TCGA data set. TCGA provides prototypical data sets for the application of AJIVE. Here we study the 616 breast cancer tumor samples from Ciriello et al. (2015), which had a common measurement set. For each tumor sample, there are measurements of 16615 gene expression features (GE), 24174 copy number variations features (CN), 187 reverse phase protein array features (RPPA) and 18256 mutation features (Mut). Two joint components are identified in the Step 2 of the AJIVE algorithm, while the second joint component is dropped in the third step. The resulting scores are visualized in this script, as in Figure 9 of the paper.

## Example of Application 2: Mortality data set

The script *Mortality/Mortality_AJIVE_Analysis.m* runs our AJIVE analysis of the Mortality data set. This data set is from the Human Mortality Database, and consists of both Spanish males and females. For each gender data block, there is a matrix of mortality, defined as the number of people who died divided by the total, for a given age group and year. Because mortality varies by several orders of magnitude, the log10 mortality is studied here. Each row represents an age group from 0 to 95, and each column represents a year between 1908 and 2002. In order to associate the historical events with the variations of mortality, columns, i.e., mortality as a function of age, are considered as the common set of data objects of each gender block. The two data blocks have been mean centered before applying the AJIVE algorithm. Two joint components are identified. The block specific loading plots and score plots of each joint and individual components are generated by this script, as in Figures 11, 12 and 13 of the paper.

## Help and Support

For questions, issues or feature requests, please reach out to Meilei Jiang: <jiangm@live.unc.edu>
