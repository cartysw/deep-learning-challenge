## Alphabet Soup Organization Analysis

## Overview

This analysis concerns a dataset of information about various different organizations that apply for funding. The goal was to create a neural network model help select successful successful organizations. Some initial data preprocessing was performed, and then a model was created. A few attempts were made to try and get the highest possible accuracy score, which will be detailed below.

## Results
Let's go over the preprocessing first.

* What were the dataset's target variables?
  * The 'IS_SUCCESSFUL' column was selected as the target because it can be used to check the accuracy of the model after training.
 
* What were the dataset's features?
  * Almost other column was used as the dataset's features (see below)
 
* A couple columns were deemed as not necessary for this model
  * The 'EIN' and 'NAME' columns were dropped because the information contained in them was not necessary for the model.
 
Now we can discuss the results. 

* How many neurons/layers/activation functions were used, and why were they used?
  * The dataset is quite large (~34k organizations!) so I opted to try the initial model with a minimal number of hidden layers (2) but with many neurons for each layer (80 for the first, and 30 for the second). The 'relu' and 'sigmoid' activation functions were chosen simply because they are a great general purpose function.

* Were you able to achieve the target model performance (75% accuracy)?
  * So the highest average accuracy percentage across each optimization attempt was 72.95%, so technically no. However, in optimization attempt V3 the last epochs were starting to test just above 75%. So yes the models technically didn't hit the target but the most recent iteration is almost there.
 
* What steps did you take in your attempts to increase model performance?
  * For optimization V1, I tried 2 different things. I tried dropping the 'SPECIAL_CONSIDERATIONS' column as it seemed like it may not be necessary. I also bumped up the neuron count for both hidden layers, which you can see below.
  * ![nnoptimizerV1](https://github.com/user-attachments/assets/172daab1-09a1-4921-b5a5-89bb4c77796d)
  * For optimization V2, since changes from V1 didn't go well I re-added 'SPECIAL_CONSIDERATIONS' and further increased neuron counts for both hidden layers. See image below for V2
  * ![nnoptimizerV2](https://github.com/user-attachments/assets/07243068-da12-41f5-9e72-28198078994f)
  * Optimization V2 didn't produce super tangible results either, so for this final attempt I added an additional hidden layer (bringing the total to 3) and further increased the neuron counts for the first 2 hidden layers. As I discussed above, this is the model that got the closest when training.
  * ![nnoptimizerV3](https://github.com/user-attachments/assets/ee933805-0131-4228-89b9-eb5ce58cfd2f)

## Summary

So overall, I wasn't quite able to hit the 75% target, but V3 is incredibly close to it. I'm pretty confident that if you increase neuron counts for each layer and/or simply run V3 again you would likely be able to hit the 75% target. While the accuracy gain from adding neurons didn't always result in higher accuracy, adding that additional layer did, so combining the 2 seems like the obvious logical next step forward towards optimization.

## Installation Instructions

* Download repository files or clone repo to your local machine
* Open any of the scripts in the 'Script' folder in your code editing software of choice (Jupyter Notebook, VSCode, etc)
* Execute individual cells or the entire script at your discretion
