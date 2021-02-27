# solution

Naive Bayes' Theorem is a classification technique based on Bayes' Theorem **under the assumption** that each explanatory variable is independent of each other. One reason why it's not used in algorithms is the mere fact that each predictor has to be *absolutely* independent of each other which is almost impossible to find in real world problems.

Another concern arises when encountering an unknown category in the test dataset's categorical variable because it didn't existed in the train dataset. The model is going to fail in making a prediction and assign zero probability instead. This phenomenon is known as **Zero Frequency**. In the real world, finding a new category that hadn't existed in the first place isn't an uncommon occurence.

#### reference
[Naive Bayes Theorem](https://www.analyticsvidhya.com/blog/2017/09/naive-bayes-explained/#:~:text=Naive%20Bayes%20Model-,What%20is%20Naive%20Bayes%20algorithm%3F,presence%20of%20any%20other%20feature.)

[back](./challenge.md)
