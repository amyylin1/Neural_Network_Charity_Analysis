# Neural_Network_Charity_Analysis

### Overview
This analysis aims to use neural network and deep learning to determine whether the best funding organization.

### Results

Data Preprocessing:

-  Target: IS_SUCCESSFUL
-  Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATION, ASK_AMT
-  Others: EIN, NAME

Compiling, training, and evaluating the model:

-  Neurons: 7
-  Layers: 2 hidden layers
-  Activation functions: relu, sigmoid

Steps I took to increase model performance:

-  Drop 'SPECIAL_CONSIDERATION' column
-  replace application_count that is less than 1000 to 'others'
-  replace classification_count that is less than 1000 to 'others'
-  add third and four hidden layers
-  increase epochs to 100
