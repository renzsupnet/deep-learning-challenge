# Deep Learning Challenge
## Data Preprocessing
### What variable(s) are the target(s) for your model?
- ["IS_SUCCESSFUL"] column is the target
### What variable(s) are the features for your model?
- X = dummy_df.drop(columns=["IS_SUCCESSFUL"]).values 
### What variable(s) should be removed from the input data because they are neither targets nor features?
- ["EIN", "NAME"] columns should be dropped
## Compiling, Training, and Evaluating the Model
### How many neurons, layers, and activation functions did you select for your neural network model, and why?
- The solution I implemented uses keras-tuner. The neurons, layers and activations will be dynamically chosen  by keras auto-tuner as manually adding neurons/layers wasn't yielding results. So the best neural network model will be dependent on the run itself as keras-tuner will determine the best automatically. Key observations from my manual tuning however indicates minimal improvements when adding layers and neurons as also reflected by keras-tuner not achieving the desired 75% target accuracy which may indicate overfitting. The dataset may be more suitable for other models instead of using keras Sequential. 3 models was defined using tuner.get_best_models(3) with their 3 parameters using tuner.get_best_hyperparameters(3).

Model 1:

![alt text](images/model1.png)

Model 2:

![alt text](images/model2.png)

Model 3:

![alt text](images/model3.png)

### Were you able to achieve the target model performance?
- No. Neither manually tuning nor using keras-tuner achieved 75% accuracy. The best model only achieved 73.56% as shown by the snippet below:

![alt text](images/accuracy.png)
### What steps did you take in your attempts to increase model performance?
- Adding layers, adding neurons and trying different activations: tanh, relu, and sigmoid.
- Defining a keras-tuner as shown below:

![alt text](images/tuner.png)