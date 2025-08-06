# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have.

## Motivation

- The motivation for creating the dataset in the first instance is unclear.  The dataset is from a speciality hospital in India and the original motivation for collecting it is unknonw.  However, the motivation for it being shared publicly appears to be to support the identification of early stage cardiovascular disease and to enable predictive machine learning models to be developed in order to achieve this
- The institution listed on the original dataset link (https://data.mendeley.com/datasets/dzz48mvjht/1) is Lincoln University College.  

Dataset citation:
Doppala, Bhanu Prakash; Bhattacharyya, Debnath (2021), “Cardiovascular_Disease_Dataset”, Mendeley Data, V1, doi: 10.17632/dzz48mvjht.1


## Composition

- Each one of the 1000 instances in the dataset represents a patient
- There are 580 positive cases and 420 negative cases of the target variable - where a positive case is where the patient has cardiovascular disease and a negative case is where they do not
- There is no missing data
- The data contains a patient identifier which on its own does not seem to fall under sensitive personally identifiable information.  However, the significance of this patient ID is not clear and it could be a meaningful identifier in certain contexts.

## Collection process

- The data was sourced from a speciality hospital in India.  It is not known how it was acquired in the first instance and over what timeframe.


## Preprocessing/cleaning/labelling

- During exploratory data analysis, an anomaly was discovered with respect to the slope indicator.  The data description on the Mendeley as well as Kaggle websites stated that there should be three values for slope - 1, 2 or 3.  The data downloaded contained 180 instances where this value was 0.  There could be several reasons for this and given the large number of occurrences, assumptions could not be made without potentially inadvertently influencing the training.  So, all of these instances were removed.
- The patient ID was removed at the start of the process in order to remove any patient-specific identifiers / variables not applicable to training.
- The raw data was saved

## Uses

- The data could be used in a clustering analysis to identify whether there are any discernable cohorts of  patients which might naturally fall into different intervention pathways

- The unexpected presence of the value 0 in the slope input feature would need to be noted.  Rather than make an assumption that the spurious category was meaningful, we decided to remove these rows to ensure a dataset which could be fully understood. Although this still leaves a sufficiently large dataset for training, future users of this dataset should be aware of this discrepancy - as there is a possibility these rows contain some critical information.

- A dataset user should be aware of the imbalance between the female and male instances in the dataset.  After removing the rows mentioned above, there are 213 female instances and 607 male instances.  Given the imbalance between female and male instances, there is a risk that a model produces poor results on the female subpopulation.  At best, this would be inaccurately predicting cardiovascular disease for healthy women - but at worse, it could be a systematic population-level health outcome inequality for women.

Models created/analysis performed should be done through the above lens.  Specifically, model performance should be assessed holistically including on these sub-groups rather than with a singular focus.  Furthermore, it might be useful to model the male and female populations separately as a way of comparing and validating the model learned from the training data.

- This dataset should not be used to generate models for cardiovascular disease prediction on a significantly different population.  The population represented here is from an Indian hospital.  Should the population being analysed be e.g. from a different country, the results from this dataset cannot automatically be applied.  It would be valid to use the learnings from this dataset to tune the direction of research on other populations - for example, to collect similar input data from the new population and compare findings.

## Distribution

- The dataset has been made publicly available online at https://data.mendeley.com/datasets/dzz48mvjht/1 and https://www.kaggle.com/datasets/jocelyndumlao/cardiovascular-disease-dataset/data.
- The original dataset link states that the data is available under a CC by 4.0 license (Creative Commons Attribution 4.0 International licence) whereas the Kaggle link states a CC0 license which has no copyright terms and conditions.  The more conservative of these is the CC by 4.0 license which means that in using this dataset, it is important to attribute it as specified on the source page, document any changes you have made in using it and state the license conditions.

## Maintenance

- It is unknown if the source dataset is maintained or updated
