# recommender-system

This is an implementation of a recommender system in Octave

Cost function and gradient descent with regularization are calculated in the file colabFilteringCostFunction.
The cost function is a sum of the squared errors for the dataset. The error is calculated as the difference between the predicted value and the actual value of some rating Y[i,j]. The error is calculated only for the data Y[i,j] for which R[i,j]=1, where R[i,j] is 1 if there is a rating and R[i,j]=0 otherwise.  

Regularization is added to the cost function with lambda paramether. The regularization is addeds as sum of squares for all the movie features X multiplied by lambda/2 and sum of squares for all user features Theta multiplied by lambda/2.

In the file colabFilteringCostFunction there is vectorized calculation for gradients for X and Theta. These two are randomly initialized before they are sent to the function. If one of these features either X or Theta was predefined, the known values would be used in the calculations.

The file normalizeRatings calculate the mean normalization for Y. Normalization is used for values in different ranges but in this case it is used to prevent zero ratings for a user that hasn't rated any movie yet. With the normalization we add the mean value to each prediction, so we avoid the zero rating. 
