# Cirrhosis-Patient-Outcome-Prediction

This repository contains the solution for the Cirrhosis Patient Outcome Prediction competition. The task is to develop a multi-class classification model to predict the outcomes of patients with cirrhosis. The model predicts the probabilities for each of the three possible outcomes: Status_C (censored), Status_CL (censored due to liver transplant), and Status_D (deceased). The performance is evaluated using the multi-class logarithmic loss metric.

## Overview
The goal of this project is to accurately predict the probability of each patient's outcome based on the given features in the dataset. The model's performance is measured using the multi-class logarithmic loss. The submission file should contain the predicted probabilities for each row in the test set.

## Evaluation Metric
Submissions are evaluated using the multi-class logarithmic loss, calculated as follows:

\[
\text{logloss} = -\frac{1}{N}\sum_{i=1}^{N}\sum_{j=1}^{M} y_{ij} \log(p_{ij})
\]

where:
- \(N\) is the number of rows in the test set.
- \(M\) is the number of outcomes (i.e., 3).
- \(\log\) is the natural logarithm.
- \(y_{ij}\) is 1 if row \(i\) has the ground truth label \(j\) and 0 otherwise.
- \(p_{ij}\) is the predicted probability that observation \(i\) belongs to class \(j\).

The submitted probabilities for a given row do not need to sum to one, as they will be rescaled prior to scoring. To avoid extremes of the log function, predicted probabilities are replaced with \(\max(\min(p, 1 - 10^{-15}), 10^{-15})\).

## Submission Format
The submission file should contain the predicted probabilities for each id in the test set, with the following format:
id,Status_C,Status_CL,Status_D
7905,0.628084,0.034788,0.337128
7906,0.628084,0.034788,0.337128
7907,0.628084,0.034788,0.337128

## Files
- `train.csv`: Training dataset.
- `test.csv`: Test dataset.
- `sample_submission.csv`: Sample submission file in the correct format.

## Acknowledgments
Thanks to the organizers of the competition for providing the dataset and evaluation framework.



