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

