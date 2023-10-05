# Q-Quant

## Notation
|     Symbol              |       Description       | 
|:--------------:          |        ------          |
| $x$                   | Data (predictor)          |
| $y$                   | Label (target)            |
| $y'$                  | Prediction                |
| $w$                   | Weights                   |
| $b$                   | Bias                      |
| $\alpha$              | $l_{1, 2}$ or Elastic Net () hyperparameter       |
| $\lambda$             | Regularization weight      |
| $\xi$                 | Slack variable            |
| $C$                   | Regularization parameter (SVM)       |

## Classification Models

|     Activity              |       Model       | Model description |
|:--------------:          |        ------    |     ------    |
| ✅    |  ```Logistic regression``` | Logistic regression is a statistical modeling technique used for binary classification and probability estimation tasks. It's a type of regression analysis that's particularly well-suited for scenarios where the dependent variable is binary (e.g., 0 or 1, Yes or No) or categorical with two classes. $Loss$ &larr; $\sum_{(x, y) \in D} -y\ln y' - (1- y)\ln(1 - y')$.|
| ✅ | $l_1$-```Logistic regression``` | $l_1$ -logistic regression or Lasso logistic regression, is a variation of logistic regression that incorporates L1 regularization. L1 regularization, in the context of logistic regression, adds a penalty term to the logistic regression cost function that encourages the model to have a sparse set of feature coefficients which helps in feature selection by driving some feature coefficients to zero, effectively eliminating them from the model. This can be particularly useful when dealing with high-dimensional data, where not all features are equally important for the classification task.  $Loss$ &larr; $\sum_{(x, y) \in D} -y\ln y' - (1- y)\ln(1 - y') + \lambda \|w\|$. |
| ✅ | $l_2$-```Logistic regression``` | $l_2$-regularization adds a penalty term to the logistic regression cost function, to encourage the model to have small, non-zero coefficients for all features. Unlike L1 regularization, which tends to drive some feature coefficients to exactly zero, L2 regularization helps in shrinking the coefficients of all features towards zero without eliminating any entirely. The main advantage of $l_2$ logistic regression is its ability to prevent overfitting by controlling the magnitude of the feature coefficients. This regularization technique can be particularly useful when dealing with correlated features or when you want to avoid excluding any features from the model entirely. $Loss$ &larr; $\sum_{(x, y) \in D} -y\ln y' - (1- y)\ln(1 - y') + \lambda \parallel w\parallel_{2}^{2}$. |
| ✅ | $l_{1, 2}$-```Logistic regression``` | Elastic Net logistic regression is a versatile modeling technique that provides a balance between feature selection and coefficient magnitude control through the combined use of L1 and L2 regularization. It is useful in situations where you need to build a predictive binary classification model while dealing with potentially correlated features and the risk of overfitting. The alpha hyperparameter allows you to fine-tune the regularization behavior to suit your specific needs. $Loss$ &larr; $\sum_{(x, y) \in D} -y\ln y' - (1- y)\ln(1 - y') + \lambda (\alpha \parallel w\parallel_{2}^{2} + (1 - \alpha) \|w\|)$. |
| ✅ | ```Support Vector Machine (SVM)``` | Support Vector Machine (SVM) is a machine learning algorithm used for classification and regression tasks. Its primary goal is to find an optimal hyperplane that best separates data points into different classes while maximizing the margin between them. SVMs are effective in handling both linear and non-linear data and have applications in various fields such as image classification, text analysis, and bioinformatics. They rely on the concept of support vectors and can use different kernel functions to transform data for improved separation. SVMs are known for their ability to provide accurate results and their versatility in solving complex problems. However, they can be computationally intensive, and hyperparameter tuning is crucial for their performance.  $Loss$ &larr; $C * \sum [ \xi + max(0, 1- y(w \cdot x + b))]$|
| ✅ | $l_1$, $l_2$, $l_{1, 2}$ - ```SVM``` | Similar to regularization used for Lgistic Regression above, L-regularized Support Vector Machine (SVM) seeks to find an optimal hyperplane that best separates data points into different classes by placing extra contraints on the coefficients of the weights. This constraints could be to promote feature section ($l_1$) or achieving a balance between maximizing the margin and minimizing classification errors while keeping the weight vector's magnitudes under control ($l_2$). $Loss$ &larr; $C * \sum [ \xi + max(0, 1- y(w \cdot x + b))] + l$-regularizer. |
| ✅ | ```Perceptron``` | The Perceptron is a fundamental concept in machine learning and artificial intelligence. It is a binary linear classifier that models a decision boundary to separate data into two classes. The Perceptron algorithm is based on the workings of a biological neuron, with inputs  being weighted and summed to produce an output. While simple, Perceptrons can be effective for linearly separable data but have limitations when dealing with complex problems. They serve as a building block for more advanced neural network architectures like multi-layer perceptrons (MLPs). $Loss$ &larr; $sign(w \cdot x + b)$.|
| ✅ | $l_1$, $l_2$, $l_{1, 2}$ -```Perceptron``` | Similar to regularization used for Lgistic Regression, regularization in perceptron including for $l_1$, $l_2$ and $l_{1, 2}$ tend towards achieving the same objectives on the coefficients, $w$. $Loss$ &larr; $sign(w \cdot x + b)+ l$-regularizer.|
| ⬜️ | ```K-Nearest Neighbour``` | KNN is based on the idea that data points with similar features tend to belong to the same class or have similar values. It makes predictions by considering the $k$-nearest data points (neighbors) in the training dataset to the data point you want to classify (for classification) or predict (for regression). It is often referred to as a lazy learner since it does not explicitly build a model during training. Instead, it stores the training data and makes predictions at runtime based on the nearest neighbors. In most cases, the choice of distance metric (such as Euclidean distance, Manhattan distance or Lorentzian distance) determines the performance of the algorithm before tuning the hyperparameter $k$.|
| ⬜️ | ```Neural Network``` | Neural network is a computational model that processes data through layers of artificial neurons, learning patterns from data to make predictions or perform tasks. Neural networks are trained by providing them with a large amount of data and allowing them to adjust the weights of the connections between nodes until they are able to produce the desired output. For example, a neural network could be trained to recognize handwritten digits by providing it with thousands of images of handwritten numbers and their corresponding labels. Once the network is trained, it can be used to recognize new handwritten digits with high accuracy.|