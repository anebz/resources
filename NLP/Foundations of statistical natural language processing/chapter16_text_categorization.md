# Chapter 16: Text categorization

Classification or categorization is the task of assigning objects from a universe to two or more classes or categories. The goal in text categorization is to classify the topic or theme of a document. As input we have a training set of objects, each labelled with one or more classes, which we encode via a data representation model. 

As test set we have data that's not been used during training. For binary classification, classifiers are typically evaluated using a table of counts. Measures can be accuracy, precision, recall. 

## 16.1. Decision trees

We classify a document starting at the top node, testing its questions, branching to the appropriate node, and then repeating this process until we reach a leaf node. Decision trees are usually built by first growing a large tree and then pruning it back to a reasonable size. The pruning step is necessary because very large trees overfit the training set. 

For growing the tree, we need a splitting criterion for finding the feature and its value that we'll split on and a stopping criterion which determines when to stop splitting. 

A problem with setting aside a validation set is that a relatively large part of the full training set is wasted, a better method is to use n-fold cross validation (section 6.2.4) to estimate a good size for the pruned decision tree. 

## 16.2. Maximum entropy modelling

It's a framework for integrating information from many heterogeneous information sources for classification. The data for a classification problem is described as a potentially large number of features. These features can be quite complex and allow the experimenter to make use of prior knowledge about what types of information are expected to be important for classification. Each feature corresponds to a constraint on the model, and then we compute the maximum entropy model, the model with maximum entropy of all the models that satisfy the constraints. 

More on generalized iterative scaling, applications to text categorization, etc. in p 591-596.

## 16.3. Perceptrons

Gradient descent, learning curve, local optimum, global optimum, backpropagation, etc.

## 16.4. K nearest neighbour classification

To classify a new object, find the object in the training set that is most similar, then assign the category of this nearest neighbour. In KNN, instead of using one nearest neighbour as the basis for the decision, we consult k nearest neighbours. The complexity of KNN is finding a good measure of similarity.

For large enough training sets, the error rate of KNN can double the Bayes error rate.

