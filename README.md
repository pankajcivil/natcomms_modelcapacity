#Guide for editors and reviewers

Custom code accompanying manuscript
> Tomasz Jetka, Karol Nienałtowski, Sarah Filippi, Michael P.H. Stumpf and Michał
Komorowski, "An information-theoretic framework for deciphering pleiotropic and noisy biochemical signaling", Nature Communications, 2018.

## Introduction

Simulations presented in the main paper are dvided into three parts:

1. R_codes
2. Matlab_codes_BA

and are structured here in seperate folders. Briefly, `R_codes` and `Matlab_codes_BA` concerns Validation Results section.

## System requirements

Codes are provided as scripts of R and Matlab enviornments and should be independent of operating system in use.
Specific requirements are listed below

### Dependencies
1. R_codes - R version >= 3.3.0, packages: ggplot2, reshape2, ggthemes, gridExtra, latex2exp
2. Matlab_codes_BA - Matlab > 2012b

### Testing
Simulations were tested using both Windows 10 and Mac OS OX 10.11 El Capitan. We used Matlab 2016b, R 3.3.0 and machine with at least 4 cores.

### Hardware
In several places, a default number of processor's cores is assumed to be present. User should adjust it to computer's capabilities. 
No additional hardware is needed.


## Installation guide

No specific installation is required. For the instruction on installing R, Matlab and required packages please see:

1. https://www.r-project.org
2. http://www.mathworks.com


## Demo

All provided codes can be run without further assistance. However, please remember to check your working directory and/or path whether it includes all needed scripts.

### Instruction to run on data

1. R_codes - There are two main files:

* capacity_validation.R - upon execution it 1) generates data (probability matrices) to use in Matlab_codes_BA; 2) calculates estimates of channel capacities. (Many) Characteristics of distributions to use in validation can be changed at the beginning of the script.
* figures_validation.R - if `capacity_validation.R` and Matlab_codes_BA have been run, it can be used for generating visualisation of results.

2. Matlab_codes_BA - if `capacity_validation.R` has ben run, falsesignal_batch.m can be run to obtain Blahut-Arimoto approximation of channel capacity.

### Expected output

1. R_codes - All results will be stored in subfolder /output/, either as .txt files (probabilitiy matrices), .rds files (R objects) or .pdfs (figures).

2. Matlab_codes_BA - All results will be stored in subfolder /output/ in .txt and .csv formats (capacity value and probability vectors).

### Expected run time for demo

Using a computer with Intel Xeon(R) CPU E5-1650 v3 3.5GHz, 6 cores (12 logical units), 32 GB RAM DDR4 2133 MHz

For a single run:

1. R_codes - estimating capacity for a single false signal distribution with fixed sd, lambda and number of molecules of receptor - less than 5 minutes (using single core)

2. Matlab_codes_BA (with default parameters) - estimating capacity for a single false signal distribution with fixed sd, lambda and number of molecules of receptor - up to 30 minutes, on average: 5 minutes (using single core)

For a full analysis as in the Main Paper: 

1. R_codes (with default parameters) - using single core, about 8 hours 
2. Matlab_codes_BA (with default parameters) - using single core, about 30 hours

## Instruction for use

See instruction in specific scripts for more assistance

### How to run the software on your data

1. R_codes - to simulate a model of receptor-ligand binding model with false signal and estimate its capacity for different false signal distribution, you need to change initial paramteres given at the beginning of the script.

2. Matlab_codes_BA - to estimate channel capacity of an arbitray discrete channel, one must specify a path to channel's probability matrix saved as a txt file.
