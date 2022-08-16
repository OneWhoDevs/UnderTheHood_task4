# UnderTheHood_task4
a simplistic algorithm or complex (choice is yours) (algorithms like logistic or single neural network) from scratch without using any deep learning API

**A binary classification model with single hidden layer**
the images used for the model are 64x64x3 images. to be fed into the model, the image-set is  FLATTENED into dimension ( 64x64x3=12288 , no_of_files) hence taking all the images in one go. each image matrix is stretched out into each column.

the trainable parameters are: W1 , b1, W2, b2.



FORWARD PROPOGATION

  Z1 :  Image matrix has dot prod with W1 (dim:(h,12288)) and each image column gets the bias column addeed on it (bias column adds on all image columns).
        the 'h' in the dimension of W1, decides the number of nodes in the first hidden layer.
  
  A1: after activation function from Z1
  
  Z2:  dot product between W2(dim=(1,h)) and A1(dim=(h,m)) gives a (1,no_of_imgs), b2 of dimenstion (1,1) is added to each column. Here we can see each column of Z2 is        a single output for each image.
  
  A2: sigmoid function on each column of Z2. Giving us a 1d array having all the outputs of for each image on each column.



BACKWARD PROPOGATION

  training is done via gradient descent algorithm. th cost function used is  ![image](https://user-images.githubusercontent.com/101567399/184948812-f6b7a607-d687-484c-9694-69ac1610f396.png)
  the derivatives for each parameters is calculated and applied to the parameters as learningrate* differential
  
  The training of the model can be visualised from the plot of the model training:
  
  ![image](https://user-images.githubusercontent.com/101567399/184942164-fed12647-d2b8-4b36-b05c-5bc3cfa27e74.png)
  
  (in case you miss this in the .ipynb file)
  
  
  function model, trains the parameters and returns trained parameters whihc can then be used for prediciton purposes.
  
