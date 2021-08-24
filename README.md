# **Arabic Semantic Error Detection and Correction**
- [Description](#description)  
- [pipeline](#pipeline)
- [Preparing the Data](#preparing-the-data)  
- [preprocessing the data](#preprocessing-the-data)
- [model](#then-we-constructed-the-model)
- [Testing](#testing)
# Description 
The project is error detection and correction for Arabic language, that correct any morphological mistake that may found in Arabic context or even misspelled word.
# pipeline
We focused on Siamese Neural Network concept to solve our problem with the help of LSTM. 
- ## Preparing the Data
1.	First, we cleaned our data from any weird character or symbol to make sure it is the data we were looking for.
2.	We then used the m2 files in QALB Dataset.
3.	We loaded in a form that suitable to all the following procedure.
4.	And split it into two variables one for the original sentence and the other for the operations done to correct those sentences.
5.	We then extracted the operations and corrected those sentences and putted it list of the target we seeking to achieve.
- ## Preprocessing the Data
1.	we prepare our input data by splitting it into tokens using different methods including NLTK tokenization.
2.	Then we created a charset that contain our alphabets and Arabic number also English numbers as it might help us in some cases also, we added to it all the symbols that will be handy in some special cases. 
3.	We then removed any character that will not be useful or identified in our char set collection using not the most convenient way but easy in modification which is regular expressions. 
4.	Later we started encoding those tokens (embedding phase) by making 3 vectors that each contains several matrices that equal to the number of tokens and its dimension is the maximum word length found in the input data tokens and the length of the charset. 
5.	We used the Siamese Neural Network concept here as we made 3 vectors 2 is input and the other one is the target.
6.	The above steps used in preprocessing the train and test data.
- ## Then we constructed the MODEL
1.	We first assigned our variables randomly the adjusted along with the testing and experimenting process. 
2.	We adjusted our architecture as we studied in all the papers, we viewed in the research process before staring the implementation. 
3.	We used Softmax activation function as we used to normalize the outputs, converting them from weighted sum values into probabilities that sum to one.
4.	We used RMSprop optimizer as it leaves the parameters at their default values (except the learning rate, which can be freely tuned).
5.	We then fitted out model by final variables (batch_size = 128, epochs = 200, latent_dim = 256)
6.	It as expected had a huge iteration and took a fine amount of time. 
7.	The validation accuracy was quite well it reached upwards 71%.
- ## Testing
1.	Definitely we started the testing by decoding a fine amount of the encoded data of course we can’t decode all the data at once and we noticed a great result 
2.	The testing phase did not stop here we used the Word Error Rate library to find the probability of that were missed by the model. 
- a.	We used part of the data in this process. 
- b.	Then we added to this function some sort of transformation which was helpful in the result by noticeable way 
- c.	The result was convenient as it showed the word error rate was almost 25% 
