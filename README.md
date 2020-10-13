# AlphabetSoupChallenge
module 19 challenge
 
#### The dataset that held the charity data was imported using pandas read_csv() and a data frame was created.  The dataframe has the following columns, and their characterizations:
#### EIN             —Identification column          -removed from dataframe
#### NAME            —Identification column          -most frequent values classified
#### APPLICATION_TYPE—Alphabet Soup application type -FEATURE: classification into 5 classes
#### AFFILIATION     —Affiliated sector of industry  -FEATURE: classification into 2 classes
#### CLASSIFICATION  —Government organization classification -FEATURE: classification into 2 classes
#### USE_CASE        —Use case for funding           -FEATURE: classification into 2 classes
#### ORGANIZATION    —Organization type              -FEATURE: classification into 2 classes
#### STATUS          —Active status                  -removed from dataframe
#### INCOME_AMT      —Income classification          -FEATURE: converted to float, used the interval midpoint and capped at 1M
#### SPECIAL_CONSIDERATIONS—Special consideration for application -removed from dataframe
#### ASK_AMT         —Funding amount requested       - converted to float
#### IS_SUCCESSFUL   —Was the money used effectively -TARGET

### Results of analysis

How many neurons and layers did you select for your neural network model? Why?

#### I ran three models, A, B, and C.  Based on the rule of thumb presented in the module, I started in Model A with three times the amount of neurons as the number of inputs.  There were 16 inputs and 2 hidden layers (layer 1 had 21 neurons and layer 2 had 27 neurons) with a total of 48 neurons.  The results for Model A: Loss: 0.5236, Accuracy: 0.7421

#### Model B also had 16 inputs and 2 hidden layers (both layers had 30 neurons each and relu activation) for a total of 60 neurons.  The results for Model B: Loss: 0.5231, Accuracy: 0.7423

#### For Model C, the inputs, layers, and neurons were the same as Model B. The only change was to the optimizer, from adam to adamax. The results for Model C: Loss: 0.5250, Accuracy: 0.7420

#### There was not much rigor to how I chose the neurons and layers, and it did not seem to change the outcome.  I did run one model that changed the activation for the first layer to sigmoid, and that model had an accuracy of 0.46.

Were you able to achieve the target model performance? What steps did you take to try and increase model performance?

#### I was not able to get beyond 75%, but I got pretty close.  Before I ran these three models, I had dropped the name column entirely.  Someone on Slack rmentioned the name column, so I went back and created new classifications based on the most frequently occurring organization names.  I got a bump up from that effort.

If you were to implement a different model to solve this classification problem, which would you choose? Why?

#### I would actually use the same model, but I would finish the name classification using regex, and I would look more carefully at all of the variables.  I think that more thoughfully representing the data would get the model to over 75% accuracy.