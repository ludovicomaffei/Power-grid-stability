# Power-grid-stability

In recent years, Smart Grid technology has gained increasing importance in the energy industry, thanks to its ability to ensure an efficient, sustainable system with low losses and high levels of security and reliability. A Smart Grid is an electrical network that efficiently integrates the behavior and actions of all connected users - generators, consumers, and those who perform both roles - in order to ensure an economically efficient, sustainable energy system with low losses and high levels of security and reliability.

In a smart grid, consumer demand information is collected, centrally evaluated against current supply conditions and the resulting proposed price information is sent back to customers for them to decide about usage. As the whole process is time-dependent, dinamically estimating grid stability becomes not only a concern but a major requirement.

Put simply, the objective is to understand and plan for both energy production and/or consumption disturbances and fluctuations introduced by system participants in a dynamic way, taking into consideration not only technical aspects but also how participants respond to changes in the associated economic aspects (energy price).

The dataset used is synthetic in nature, meaning the data has not been collected from real-world observations. The dataset was generated through simulations of an electrical system that features a star topology with four nodes.

![Screenshot 2024-03-02 alle 16 53 33](https://github.com/ludovicomaffei/Power-grid-stability/assets/161887676/77f62df8-81c5-430e-9bc8-16590b0c8e20)

The original dataset contains 10,000 observations. As the reference grid is symetric, the dataset can be augmented in 3! (3 factorial) times, or 6 times, representing a permutation of the three consumers occupying three consumer nodes. The augmented version has then 60,000 observations. It also contains 12 primary predictive features and two dependent variables.

For performing the prediction measurements, a Feed-Forward Neural Network was used, consisting of an input layer with 12 neurons (one for each predictive feature), three hidden layers with 24, 24, and 12 neurons respectively, and one neuron for the output layer. The ReLU activation function was chosen for the neurons in the hidden layers, and the sigmoid activation function, suitable for binary classification cases, was chosen for the neuron in the output layer. 

To train the neural network, the dataset was divided into a training set and a validation set, with proportions of 90% and 10% respectively. The chosen technique for model training was K-fold cross-validation, which divides the training set into K equal parts, in this case, 10, called folds. The model is trained K times, using a different fold as the test set at each iteration and the remaining folds as the training set. The model's performance is evaluated on each test set, and evaluation metrics are calculated by combining the results of the K iterations. The model is trained for 50 epochs.

Subsequently, the model's performance is evaluated on the validation test by calculating the accuracy of the confusion matrix.
The achieved accuracy was 98.25%.

