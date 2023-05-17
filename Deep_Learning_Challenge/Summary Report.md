OVERVIEW

The purpose of this analysis was to assist a nonprofit foundation, Alphabet Soup, in developing a tool to easily identify future applicants that have the best chance of suceeding in their venture.  to achieve this goal, a neural network model was developed to screen applicants and predict success.  Alphabet Soup supplied a history data file with 34,000+ applicants for funding and whether or not they were successful with their venture.


RESULTS
After looking at the data supplied by Alphabet Soup, the success column was determined as the target for the model since that was the ventures that they wanted to fund.  The following were features of the model:
- Identification number & name of applicant
- Alphabet Soup's application type
- the affliated sector of the inducstry
- Goverment organization classification
- the use case for funding
- organization type
- the active status
- income classification
- were any special considerations taken
- funding request amount
- project success status

The identifcation number and name of the applicant was removed from the data set since they would have no bearing on the model.  The application type and government classification data was reduced by binning together some of the one off types into an other category to help improve the performance of the model.  Once the data was organized as needed, it was split into a set to train the model and a second set to be able to test the performance.

The inital model created had the following:
- 2 hidden layers, the first with 43 input units and an output of 80 units and the second with an output of 30 units.  
- Both hidden layers used the "relu" activation
- the output layer had 1 output unit and utilized the "sigmoid" activation

Once trained and tested, this initial model fell short of the 75% accuracy target only achieving 73.0%

Several tweaks to the model were conducted in attempt to improve its accurancy:
- the number of values put into the "other category" for application type and government classification was reduced -- this only improved the accuracy to 73.2%
- additional neurons were added to the 2 hidden layers -- the accuracy rating didn't change and remained 73.2%
- the data was examined for outliers and they were removed from the 'Status' & 'Ask Amount' fields and a new model trained -- the accuracy of this model improved to 74.4%.  Better but still short of goal
- Keras-tuner was utilized to try multiple factors including different activations, optimizers, numbers of layers, and number of neurons.  The best model from the auto-tuner returned a result of 74.9% accuracy.


SUMMARY
Multiple models were created to predict funding success and they all fell short of the goal of 75%.  The best solution I was able to provide Alphabet Soup was a model that predicted success coreectly 74.9% of the time.
