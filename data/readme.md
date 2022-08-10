# Overview

This folder contains all of the data for this analysis (pre- and post-processing and cleaning).

## Raw Data 

The `raw_data` folder contained the data directly downloaded from the Qualtrics survey for each facility location. Due to confidentiality reasons, the raw data is not publicly available.

This folder also contains two other reference dataframes:

* `answerkey.csv`: the code types and identifications according to each facility's EOP
* `colnames.xlsx`: a dataframe with new column names (used in the data cleaning process)
* `codekey.csv`: contains the codes for each emergency

## Graded Data

The `graded_data` folder contains the results from each facility following cross-referencing with their EOP.

* `FacilityA_grades_processed.xlsx`
* `FacilityB_grades_processed.xlsx`
* `FacilityC_grades_processed.xlsx`
* `FacilityD_grades_processed.xlsx`
* `FacilityE_grades_processed.xlsx`

## Processed Data

The outputs of the markdowns in `/code/processing_code` are stored in the `processed_data` sub-folder. Processed datasets are saved as .rds to preserve all data types and classes, thus avoiding having to redefine data types in subsequent markdowns.

The facility-specific processed dataframes are not publicly available, due to confidentiality reasons. However, the folder does contain the following dataframes:

* `combined_processed.rds`: the initial dataframe with all facility-specific dataframes
* `analysis_processed.rds`: contains only the demographic and code experience variables
* `full_processed.rds`: contains all variables captured in the survey (including free responses)

See `/code/readme.md` as well as the source markdowns for more detail about how each processed dataset was generated.


