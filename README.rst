Fork of the https://github.com/scikit-learn/scikit-learn.

Differences:

1. We have passed sample_weights parameters to the Liblinear SVM solver (LinearSVC classifier).

2. We have added the following parameters to the fit method of the SVC class (LibSVM-based classifier):

*feature_weight - array of booleans, it defines if a particular feature is considered in the SVM training process

*sample_weight - array of reals, it defines if a particular sample is considered in the SVM training process

*samples - training data array (without labels).

These changes are made to simplify the use of the LinearSVC/SVC classifiers to train decision stamps in oblique or non-linear decision trees like: https://github.com/masterdoors/kernel_trees. 

They help to adjust sample weights depending on the contribution of those samples to the utilized impurity criterion.

They help to get rid of storing support vectors for each decision stamp (it leads to large memory consumption for deep trees).
