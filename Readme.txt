This file describes contents of the zipped files Datasets.zip and ISWC2017Evaluation.zip
1. Datasets.zip contains a directory "csv" that contains the 60 datasets used for evaluation downloaded from https://data.gov.in/

2. ISWC2017Evaluation.zip contains folders - "csv" and "EvalSheets" and files - ISWC2017Evaluationdatasetdetails.xlsx and MLEvaluate.R

3. ISWC2017Evaluationdatasetdetails.xlsx contains the metadata regarding the datasets.

4. "EvalSheets" folder contains files starting with RML_ and RNonML_

5. Files starting with RML_ are the Schematic Integration outputs from the "BASE + ML + SEMANTICS" Model for the evaluation datasets. Schematic Integration reports for each dataset, the theme relating to the table, anchoring column, connected column and the property that best describes the relationship between the anchoring column and the connected column. The  column "LVCol" reports whether the column is a literal-value column (0: Not a literal-value column, 1: literal-value column) and column "PropScore" given by the evaluators captures whether the the property identified by the model correctly captures the correct relationship between anchoring column and connected column (0: Incorrect, 1: Correct, NULL:Model cannot classify). Evaluators evaluated only literal-value columns. 

6. Files starting with RNonML_ are the Schematic Integration outputs from the "BASE" Model for the evaluation datasets. Schematic Integration reports for each dataset, the theme relating to the table, anchoring column, connected column and the property that best describes the relationship between the anchoring column and the connected column. The  column "LVCol" reports whether the column is a literal-value column. The "BASE" model reports properties for literal-value columns as the column name literal of the connected column.

7. MLEvaluate.R is the R code that summarises evaluation results using the evaluation outputs mentioned in 5. and 6.

------------------------------CHANGES AFTER INCORPORATING ISWC REVIEW COMMENTS--------------------------------------------------

MLEvaluate.R: Section included for Confusion Matrix.
True Positives (TP) : literal-value columns where a valid LOD property has been identified and "PropScore" = 1 (Correct Classifications)

False Positives (FP) : literal-value columns where a valid LOD property has been identified and "PropScore" = 0 (Incorrect Classifications)

True Negatives (TN) : literal-value columns where no valid LOD property has been identified and "PropScore" = NULL (Model cannot classify)

False Negatives (FN) : literal-value columns where no valid LOD property has been identified and "PropScore" = 0. These are columns where the model should have classified but did not classify

Error <- (FP + FN)/nLV
Accuracy <- (TP + TN)/nLV
Precision <- TP/(TP + FP)
Recall <- TP/(TP + FN)
F1 <- 2*Precision*Recall/(Precision + Recall)

nLV denotes the total number of literal-value columns.

