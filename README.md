# Neural_Network_Charity_Analysis

## Overview
We are using data from charities which received funding. We are using neural networks to analyze this data to predict which organizations receiving funding will be successful.

## Results
Results can be summarized as follows:

### Data PreProcessing
To get our data in a state to be useful in a neural network we needed to identify the target for the model, the features, and remove extra data.
 - Target: IS_SUCCESSFUL
 - Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, ASK_AMT, and SPECIAL_CONSIDERATIONS (in some models)
 - Removed Data: EIN, NAME (SPECIAL_CONSIDERATIONS in some models)
 
 Our removed data was simply the identifing data, so it was not useful and would throw off the model if included. SPECIAL_CONSIDERATIONS was excluded in later models to try and remove extra noise. It did not impact the accuracy much, if at all.
 
![ids](/Resources/ID_Columns.PNG) 

In addition to this the CLASSIFICATION and APPLICATION_TYPE columns were also binned into OTHER groups where, based on the density or frequency of occurrence, it didn't make sense to call out the individual values.

![density](/Resources/Density.PNG)

### Compiling, Training, and Evaluating the Model
 - Our initial model included 2 hidden layers with 80 and 30 neurons, respecitvely. We used a sigmoid activation function as that is what we have used to this point.
 - Our target model performance was set at 75%, which we did not meet. We did however get close at slightly over 72% consistently.
 - Attempting to get to 75%, I removed the SPECIAL_CONSIDERATIONS column in an attempt to remove some noise from the model. I also attempted to add more neurons in our 2 layers and to add an additional hidden layer. Unfortunately, none of these three attempts got our model above 72% accuracy.

## Summary
Overall, we accomplishe approximately 72% accuracy in each of our models. As we did not achieve our 75% accuracy goal, further adjustments would be necessary. To begin, we should bucket the ASK_AMT column or throw it out all together since there are so many unique values. Binning using certain ranges would likely be a good start, but if this process was too intensive, dropping it to keep the model more simple may be the best call. 

![values](/Resources/Unique_Values.PNG)

Also, using a less computationally intensive modle, such as a Random Forest model, may be best as the data here is not too large of an amount and could be more efficient.