This file describes contents of the zipped files Datasets.zip and ISWC2017Evaluation.zip
1. Datasets.zip contains a directory "csv" that contains the 60 datasets used for evaluation downloaded from https://data.gov.in/

2. ISWC2017Evaluation.zip contains folders - "csv" and "EvalSheets" and files - ISWC2017Evaluationdatasetdetails.xlsx and MLEvaluate.R

3. ISWC2017Evaluationdatasetdetails.xlsx contains the metadata regarding the datasets.

4. "EvalSheets" folder contains files starting with RML_ and RNonML_

5. Files starting with RML_ are the Schematic Integration outputs from the "BASE + ML + SEMANTICS" Model for the evaluation datasets. Schematic Integration reports for each dataset, the theme relating to the table, anchoring column, connected column and the property that best describes the relationship between the anchoring column and the connected column. The  column "LVCol" reports whether the column is a literal value column and column "PropScore" given by the evaluators captures whether the the property identified by the model correctly captures the  relationship between anchoring column and connected column. Evaluators evaluated only those literal value columns for which a valid property has been identified by the model.

6. Files starting with RNonML_ are the Schematic Integration outputs from the "BASE" Model for the evaluation datasets. Schematic Integration reports for each dataset, the theme relating to the table, anchoring column, connected column and the property that best describes the relationship between the anchoring column and the connected column. The  column "LVCol" reports whether the column is a literal value column.The "BASE" model does not identify relevant properties for literal value columns. The properties are reported by the model as the column name literal of the connected column.

7. MLEvaluate.R is the R code that summarises evaluation results using the evaluation outputs mentioned in 5. and 6.


