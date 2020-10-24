# Decision-treee
# classification
Decision trees are popular supervised learning method used for both regresion and classification .DT are good exploratory method ,give a better idea about what the influential features are in the dataset

DT learn a series of Explicit if then rules on features value that results in a decision that predicts the target value.

we can generalsie the idea of finding a set of rules to categorize an object into correct category to many other classification task

eg:here the task involves finding rules that can predict what species a particular flower is based on measurments of certain parts of the flower.Rather than try to figure manually for every task.In iris dataset we have 3 different species of flowers

goal of bulding a DT is to find the sequence of qu that has best accuracy  at classify the data in fewest steps

each descision splits the data into 2 branches based on same feature value being aove or below a threshold

eg:petal lenght lessthan 2.35cm is an example of splitting rule that treshold is called split point

An example of an informative split might be to put all instances of the flowers with
petal length less than 2.35 centimeters into one bin and the rest in the other bin

**an inpotant concept is how informative a split of the data is**

So for the best split,
the results should produce as homogeneous a set of classes as possible

# bulding of DT

So to build the decision tree,the decision tree building algorithm starts by findingthe feature that leads to the most informative split. For any given split of the data on a particular feature value,even for the best split it's likely that some examples willstill be incorrectly classified or need further splitting

We can continue this process recursively until we're left with leaves inthe decision tree that all have the sameor at least a predominant majority of a target value. 

Trees whose leaf nodes each have all the same target value are called pure,as opposed to mixed where the leaf nodes areallowed to contain at least some mixture of the classes

# prediction
To predict the class of a new instance given its feature measurements,using the decision tree we simply start at the root of the decision tree and takethe decision at each level based onthe appropriate feature measurement until we get to a leafnode. 

**The prediction is then just the majority class of the instances in that leafnode**

# Regression with DT
Decision trees can also be used for regression using the same process of testing the future values at each node and predicting the target value based on the contents of the leafnode. For regression, the leafnode prediction would be the **mean** value of the target values for the training points in that leaf. 

So when building decision trees, we need to use some additional strategy to prevent this **overfitting**. One strategy to prevent overfitting is to prevent the tree from becoming really detailed and complex by **stopping its growth early**. This is called pre-pruning. Another strategy is to build a complete tree with pure leaves but then to prune back the tree into a simpler form. This is called post-pruning or sometimes just pruning.

We can control tree complexity via pruning by limiting either the **maximum depth** of the tree using the max depth parameter or the maximum number of leafnodes using the **max leafnodes parameter**. We could also set a threshold on the minimum number of instances that must be in a node to consider splitting it.
 
 # key parameter

**max_depth**:controls maximum depth(n.o of split points).Most common way to reduce tree complexity overfitting.

**min_samples_leaf**:threshold for the minimum of data instances of leaf can have to avoid further splitting

**max_leaf_nodes**:limit total n.o of leaves in tree

In practise adjusting max_depth is enough  to reduce overfitting

# looking at feature importance
Another way of analyzing the tree instead of looking at the whole tree at once is to do what's called a feature important calculation. And this is one of the most useful and widely used types of summary analysis you can perform on a supervised learning model. 

*Feature importance is typically a number between 0 and 1 that's assigned to an individual feature.

*It indicates how important that feature is to the overall prediction accuracy. A feature importance of zero means that the feature is not used at all in the prediction.

* A feature importance of one, means the feature perfectly predicts the target. 

*Typically, feature importance numbers are always positive and they're normalized so they sum to one

n scikit-learn, feature importance values are stored as a list in an estimated property called feature_importances_. And note the underscore at the end of the name which indicates it's a property of the object that's set as a result of fitting the model and not say as a user defined property
