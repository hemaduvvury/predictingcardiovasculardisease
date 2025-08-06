# Model Card

  See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration.

## Model Description

**Input:** Tabular data with each row representing an individual person and containing a mix of categorical, ordinal and numeric input variables.

**Output:** A binary classification decision.  A positive classification is a prediction of cardiovascular disease whereas a negative classification is a prediction of no cardiovascular disease in that person.

**Model Architecture:** The model is a decision tree classifier.  It has been tuned on a variety of hyperparameters to produce optimal recall scores and to enable intuitive interpretation by clinical end users.

## Performance

The below captures the cross validation and test results of the decision tree classifier.  The cross validation measures are based on a 5-fold stratified cross validation performed on the training data and the test scores represent the scores achieved by the model on unseen test data.  The training data represented 80% and the test data 20% of the instances in this dataset.

Mean cv accuracy:	0.884155
Mean cv recall: 	0.984711
Mean cv: f1 0.922071
Test accuracy:	0.871951
Test recall:	1.0
Test: f1 0.921348


It is worth noting that the decision tree classifier achieved a 100% recall on both the training and the test set, and additionally on the male and female subpopulations.  This is highlighted in the scores below.

Model	Tuned accuracy 0.871951
Tuned recall: 1.0
Tuned f1:		0.921348
Tuned recall male:	1.0
Tuned recall female: 	1.0


Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on.

## Limitations

This model was developed using a patient population from an Indian speciality.  It is intended to be used as a cardiovascular prediction aid to clinicians who are working with patients from the relevant population pool.  It is also intended to provide some insight into which key clinical input variables are most predictive of cardiovascular disease.  The model and the predictive analysis accompanying it cannot be meaningfully used on meaningfully different population groups.

## Trade-offs

The model exhibits tradeoffs in the overall accuracy and the precision of positive case identification due to the focus on the recall score in its tuning phase.  The f1 score which gives a balanced view of precision and recall scores dropped after tuning and the overall accuracy dropped even more.  Multiple tuning rounds across a rane of scores could be performed in order to determine if there is a more optimum score balance for the specific objective at hand.
