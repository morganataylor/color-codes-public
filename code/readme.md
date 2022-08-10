# Code Folder Overview
This folder stores all of the scripts that process and analyze the data. There are two sub-folders: `processing_code` and `analysis_code`, the contents of which are described below.

# Processing
The `processing_code` folder contained markdowns for each facility as well as an overall combined processing markdown.

## Facility Specific Markdowns
Due to confidentiality reasons, these markdowns are not publicly available as they contain facility identifiers. However, each markdown followed these steps:

* Remove junk headers and empty columns
* Concatenate answer code columns for each answer
* Remove redundant columns
* Remove test responses from research team
* Relabel columns
* Replace blanks with NA
* Adjust data classes as needed
* Save cleaned file

## Combined Processing Markdown: `processing-combined.Rmd`
This markdown combines the graded dataframes from each facility into one overall dataset. This process includes the following steps:

* Load graded facility data
* Make column names consistent
* Combine the dataframes
* Clean variables (i.e. clean labels for the more open-ended variables)
* Remove outliers/left over responses from research team
* Save processed file

## Analysis Processing Markdown: `processing-analysisdata.Rmd`
This markdown imports combined processed dataframe and prepares it for analysis of the confidence scores and code identification scores. The workflow includes the following steps:

* Drop variables relating to specific codes
* Categorize all variables as 0, 1, 2, ...
* Convert Code Identification score to percentage
* Define `delta` to be change in confidence score
* Drop any remaining unnecessary variables
* Save newly processed dataframe for analysis

# Analysis
The `analysis_code` folder contains the code used for the data analysis.

## Exploratory Analysis Markdown: `analysis-eda.Rmd`
This markdown imports the processed data and conducts the exploratory data analysis. It examines the predictors of performance on the code survey. In terms of the dataset, the three (potential) outcomes of interest are Overall Grade (`GradeOverall`), Code Type Grade (`GradeType`), and Code Answer Grade (`CodeScore`).

It also creates the initial summary tables in the manuscript.

## Facility Codes Markdown: `analysis-facilitycodes.Rmd`
This markdown imports the answer key for each facility and creates a visualization of the answers.

## Code Analysis Markdown: `analysis-codes.Rmd`
This markdown imports the processed data and analyzes participant performance by emergency.

## Pre/Post Confidence Score Markdown: `analysis-prepost.Rmd`
This markdown imports the processed data and analyzes the pre/post confidence scores. It conducts the overall paired T-test and examines the scores by variables included in the analysis.

## Bivariate Analysis for Demographics Variables: `analysis-bivariate-demographics.Rmd`

For each variable, the following steps are taken:

* Summary statistics
* ANOVA
* ANOVA with Tukey correction
* Box Plot Visualization if significant

## Bivariate Analysis for Experience with Code Variables: `analysis-bivariate-experience.Rmd`
This markdown imports the processed analysis data and conducts a bivariate analysis for the outcomes of interest: change in confidence score and code identification score.

For each variable, the following steps are taken:

* Summary statistics
* ANOVA
* ANOVA with Tukey correction
* Box Plot Visualization if significant

## MVR Analysis Markdown: `analysis-mvr.Rmd`
This markdown conducts the multivariate regression with code identification accuracy and generates the final table in the manuscript.