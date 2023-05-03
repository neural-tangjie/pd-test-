# AI-based PD diagnostic predictions

## 1 System requirements

```
Hardware requirements: 
    main.py requires a computer with enough RAM to support the in-memory operations.
    Operating system：windows 10
    
Code dependencies(environment.txt):
    python == 3.8.7 
    torch == 1.13.0 + cu116
    numpy == 1.21.0
    sklearn == 0.0
    pandas == 1.3.5
    ...
```

2 Quick Setup
-----------

1.Clone the InnerEye-DeepLearning repo by running the following command:

```
git clone {待填充}
```

2.Create and activate your environment:

```
pip install -r environment.txt
```

## 3 Instructions for use

Verify that your installation was successful by running the main.py model

```
  python main.py --model --n_classes
```

**Parameter description**

```
'''
  --model = {"XGB-RFE","RF-RFE","GBM-RFE"}
      --model stands for the AI model used by the program
  
  --n_classes = {"2","3"}
      --n_classes represents the number of categories that belong to the data that is used
'''
```

## 4 Description of the method

In recent years, machine learning has become an effective means of analyzing and processing diverse datasets to gain a comprehensive understanding of the relationships between different components of metabolomics data with differing concentrations and reaction characteristics. By establishing machine learning models to predict the links between specific metabolic pathways/metabolites and diseases, we can discover new biological insights.

### Random Forests

Random Forest Algorithm, often referred as RF,is a kind of ensemble learning algorithm based on decision tree.(Elith, Leathwick et al. 2008). We used the Gini coefficient as a dividing criterion

### Gradient Boosting Machine

(Gradient Boosting Machine) create a model with high performance, using weakly independent learners.(Friedman 2001) . The number of weak classifiers (n_estimators) was set to 200 and the maximum depth of the tree (max_depth) to 10

### eXtreme Gradient Boosting

XGB is an optimized distributed gradient enhancement model. It continuously builds CART trees (Classification and Regression Trees) based on the direction of gradient descent of the loss function, and gradually approaches the local minimum of the loss function to finally build a strong classifier with high accuracy.(Chen and Guestrin 2016). The max_depth was set to 5.

### Recursive Feature Elimination

RFE is a recursive feature elimination algorithm.It obtains the optimal combination of variables that maximizes the model performance by adding or removing specific feature variables.(Chen and Jeong 2007) In RFE algorithms, we add another layer of resampling process (10-fold cross-validation)  to the outer layer of the aforementioned algorithm in order to better evaluate the performance fluctuations in the feature selection process.

## 5 Contact

If you have any feature requests, or find issues in the code, please create an issue on GitHub.

Please send an email to 1120200076@bit.edu.cn] if you would like further information about this project.
