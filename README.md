# Neural_Network_Charity_Analysis

### Overview
This analysis aims to use neural network and deep learning to determine the factors that contribute to a successful funding organization.

### Results

Data Preprocessing:

-  Target: IS_SUCCESSFUL
-  Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATION, ASK_AMT
-  Others: EIN, NAME

Compiling, training, and evaluating the model:

-  Neurons: first layer (15), second layer (7)
-  Layers: 2 hidden layers
-  Activation functions: first and second layer (relu), output layer (sigmoid)
-  I was not able to acheive the target model performance even for the modifications I did below.  
- Steps I took to increase model performance:

1.  drop 'SPECIAL_CONSIDERATION' column (less important)

         application_df=application_df.drop(['EIN','NAME', 'SPECIAL_CONSIDERATION'], 1)
        
2.  replace application_count that is less than 1000 to 'others' (filter out the less frequent event)
         
         replace_application=list(application_count[application_count<1000].index)
         
3.  replace classification_count that is less than 1000 to 'others' (filter out the less frequent event)

        replace_class=list(classification_count[classification_count<1000].index)
        
4.  add third and four hidden layers (more computation power)

        # third hidden layer
        nn_model.add(tf.keras.layers.Dense(units=60, activation='relu'))
        
        # fourth hidden layer
        nn_model.add(tf.keras.layers.Dense(units=40, activation='sigmoid'))
        
5.  increase epochs to 100
        
        # train the model
        fit_model = nn_model.fit(X_train_scaled, y_train, epochs=100)
        

### Summary

Overall, the model performs rather poorly (high loss and low performance). The raw data may contain outliers and noisy variables that distract the performance. 
