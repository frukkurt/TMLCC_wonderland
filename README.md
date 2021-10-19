# Thailand Machine Learning for Chemistry Competition 2021 (TMLCC 2021)
## TEAM: WONDERLAND


![OPENER](https://user-images.githubusercontent.com/63940535/137848377-88df5b91-f43e-403b-9996-0ae2ff380a27.gif)

## Content

- Data understand
- Data cleaning
- Feature selection
- Data preprocessing
- Model 
- Summary

## What we do (TARGET)
![TMLCC_Wonderland (12)](https://user-images.githubusercontent.com/63940535/137857699-ddbd9a22-3ec8-4ad6-92c6-0ba43688110a.gif)



## I.Data understand
or Exploratory data

<img alt="Screen Shot 2564-10-19 at 12 43 37" src="https://user-images.githubusercontent.com/63940535/137850634-9f50b97f-e68d-40ff-953d-951a605904a7.png">

| **Feature** | **Dtypes** |
| ----------- | ----------- |
| MOFname | str |
| volume [A^3] | float |
| weight [u] | float |
| surface_area [m^2/g] |float |
| void_fraction | float |
| void_volume [cm^3/g] | float |
| functional_groups | str |
| metal_linker | class |
| organic_linker1 | class |
| organic_linker2 | class |
| Topology | str |
| CO2/N2_selectivity | float |
| heat_adsorption_CO2_P0.15bar_T298K [kcal/mol] | float |
| For Predict | float |
| CO2 working capacity | float |

<img alt="Screen Shot 2564-10-19 at 12 34 39" src="https://user-images.githubusercontent.com/63940535/137849719-e600a89a-ea29-4715-a972-9cb8385c4646.png">


## II.Data cleaning
![TMLCC_Wonderland (11)](https://user-images.githubusercontent.com/63940535/137857373-38a00f4f-1d48-42f4-92d7-b9f383fcc0f0.gif)

- Drop `NaN` `null` 
- Fillter data (Eg. void volume , void_fraction) 

<img alt="Screen Shot 2564-10-19 at 12 37 17" src="https://user-images.githubusercontent.com/63940535/137850001-fc392998-c00c-46ad-b69d-5f55b8cfd934.png">


## III.Fearure selection 
and feature engineering

### Selection
- **Correlation plot** (Cut : Weight because lower correlation with CO2 working capacity)
### Engineer
- **Compute** : Density
![TMLCC_Wonderland (3)](https://user-images.githubusercontent.com/63940535/137850372-6afb2a2a-94cf-4694-968c-2c6cae7d6862.gif)


## IV.Data Preprocessing

![TMLCC_Wonderland (5)](https://user-images.githubusercontent.com/63940535/137851062-3802ad93-8c5d-4ad6-8865-a0eedfa6287c.gif)

because the model understands the data in Numerically only, we convert the data into a computable format.

- **ONE-HOT ENCODE** : Class or string data types

- **NORMALIZATION** : Numerical , Continue data types

## V.MODEL



![TMLCC_Wonderland (8)](https://user-images.githubusercontent.com/63940535/137851976-f09dc363-a3a8-4365-b51c-2727204fa2e1.gif)

we used model :
- **Genetic programming** : Use genetic algorithm to randomize equations or rules of relativity. In prediction, there are advantages that we can explain the equations. The disadvantage is that it takes a long time to find the equations.
- **Voting regressor** : Using multiple models to predict Where any model predicts close to the real value, it gives a lot of weight to that model. Then do a weighted average of the calculated values with other models. The advantage is that it can reduce overfitting very well. Disadvantages may take a long time because there are many models that need to be trained and there may be a high error if there is a model that is distorted from real value very much.
- **Random forest** : It is a random decision tree with different structures based on a given value, it looks like a forest, and then selects the best one tree.The advantage is that it is difficult to overfit and does not need to normalize the data. The disadvantage is that it takes a long time and may be difficult to find the best value because it is random.
- **Neural network** : Neural Network is a neural network. It is a branch of artificial intelligence. Artificial Intelligence (AI) is a concept that designs computer network systems. to mimic the work of the human brain.
- **XGboost** : Is an algorithmthat the model learns the error value from the previous model and can also choose the number of cores in the calculation. The advantage is that it can fit the data quickly, does not need to normalize the data first, and is strong to outlier. The disadvantage is that it is easy to overfit because it can modify the model from the previous model and may also be equipped with Local optimal.

## VI.Summary
We used metric Mean absolute error for Evaluation & Validation.

![TMLCC_Wonderland (9)](https://user-images.githubusercontent.com/63940535/137855381-8c5c37a7-57e9-4af7-a007-248f153c94b3.gif)

| **Algorithm** | **Train (MAE)** |**Test (MAE)** |
| ----------- | ----------- |----------- |
| Genetic programming | N/A | 35.00 |
| Voting regressor | N/A | 23.65 |
| Random forest | 7.57 | 19.55 |
| MNeural network | 25.22 | 13.28 |
| XGboost | 8.88 | 18.18 |

The team did not validation the **Genetic programming model** and **Voting regressor model**.It can be noticed that **Neural network** under fitting occurs due to The structure may not be good enough and the number of epochs is too young. In **Random forest**, there is a high chance of overfitting and poor predictive results. Compared to **XGboost**, it's almost overfitting and has the best predictions.


[![YOUTUBE PRESENTATION]](https://youtu.be/Q5YEv2AkOT8)
