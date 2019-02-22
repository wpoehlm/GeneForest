# GeneForest
The goal of this repository is to simplify gene discovery from RNA expression data using Random Forests in Python.  Instead of having to write or modify source code, users must provide two properly formatted input files.  

# Software dependencies

Python3 with the following libraries:
numpy
pandas
scipy.stats
sklearn
seaborn

# Input Files
A user must provide a gene expression matrix (GEM) and a sample annotation table

## Gene Expression Matrix (GEM)

A tab delimited table of gene expression values must be provided.  The first column should contain Gene IDs, with no header for this column.  For example: 

| Sample1 | Sample2 | Sample3 | Sample4 | Sample5 |         |
| ------- | ------- | ------- | ------- | ------- | ------- |
| Gene1 | 0.215 | 12.770 | 15.112 | 12.111 | 501.211 |    
| Gene2 | NA | 10.265 | 50.555 | NA | 423.221 |
| Gene3 | 0.212 | 0.472 | 12.223 | 111.121 | 456.778 |
| Gene4 | 0.543 | 0.778 | 23.421 | 224.431 | 333.421 |
| Gene5 | -5.012 | 0.783 | NA | 353.765 | 334.431 | 

It is currently expected that the matrix is log2 transformed and missing values are specified as 'NA'.  

## Sample Annotation Table 

A tab delimited table that contains a column for Sample IDs and a column for sample attributes must be provided. The first column should contain the Sample IDs and each additional column provides information about sample attributes.  All attributes are expected to be categorical.  A header is expected for each column but the content of the header is flexible. The sample ID's in the first column must match the header of your GEM input.  For example:

| Sample | Cancer | Tumor | Gender | Vital Status |      
| ------- | ------- | ------- | ------- | ------- |
| Sample1 | KIRC | Primary | Male | Dead |    
| Sample2 | KIRC | Primary | Male | Alive |
| Sample3 | KIRP | Adjacent Normal | Female | Alive |
| Sample4 | KICH | Primary | Female | Dead | 333.421 |
| Sample5 | KIRC | Adjacent Normal | Female | Alive | 

### todo
- Add hyperparameter sweep
- Make command line friendly script and improve code documentation/usability
