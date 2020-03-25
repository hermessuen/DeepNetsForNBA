# DeepNetsForNBA

I built a Deep Learning Network for NBA game prediction. Game data from 2004-2020 were used. An exponential moving average of the home teams and away team's previous 10 games were taken for the following statistics:

1. Points
2. FG percentage
3. FT percentage
4. Three-Point percentage
5. Assists
6. Rebounds

The exponential average of all these features were used as predictors for whether or not the home would win the game. An exponential average of the previous 10 games were used to make sure that the network did not "see into the future". i.e. was not trained to predict something using data that had already happened

In an effort to make the network more predictable, differential statistics (the difference between the home team stats and the away teams stats) were calculated as well. For more features, I also took the ratio of the home team stats with the away team stats. 

The network used the following strucutre:
10-5-2 

The numbers represent the size of the hidden layers. The output layer contained two neurons, representing the probabilites that the network predicts for the home team to have won the game. Leaky ReLu units were used as the activation function. The loss function was the binary cross-entropy loss after converting the final layer values to probabilites using a softmax function. 

The network was used as part of a learning exercise about how to properly optimize a deep network. Thus, I experimented with several different learning algorithms: stocastic gradient decsent (with momentum), Adam, and RMSprop. Various settings for Mini-batch, learning rate, and gradient clipping were used to try to improve network performance, particularly generalization accuracy. 

The PowerPoint provides all the relevant concepts surrounding how to optimize a deep network. 
