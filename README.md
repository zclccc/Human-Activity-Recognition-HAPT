# Human Activity Recognition
Human Activity Recognition (HAR) based on sensory data is an active research field of classifying data recorded by sensors into known well-defined movements. A challenging problem is dealing with the large number of time-series data and finding a clear way to match data to corresponding movements. We propose a generic framework to predict sequences of human activities from sequences of inertial sensor data. 

Please check further details in ```HAPT_paper.pdf```.
## Table of contents
* Dependancy
* Dataset
* Usage
* Authors

## Dependancy
Project is created with:
- Python 3.6
- Tensorflow 2.0.0

## Dataset
Human Activities and Postural Transitions Dataset (HAPT)

## Usage
Unzip hapt_tfrecords.7z in a folder called hapt_tfrecords in the root directory of HAPT. Manipulate ```confin.gin``` to switch from different modes. And use```python3 main.py``` to start the program.

### Tuning Mode
Under this mode, no checkpoint will be saved and nothing will be visualized. And Bayesian Optimization will be executed.
```
main.tuning = True

main.unit = 48 #this hyperparameter will not be executed.
main.learning_rate = 0.0012 #this hyperparameter will not be executed.
main.dropout = 0.08 #this hyperparameter will not be executed.
main.num_epoch = 5 #the epochs you want to run#
```

### Non-tuning Mode
Under this mode, you will have control of the hyperparameters for a single run. Checkpoints will be saved for every 5 epochs. If there is previous checkpoint, it'll be restored automatically. A random segment of sequence in test set will be visualized.
```
main.tuning = False

# all hyperparameters belows could be manipulated as you wish
main.unit = 48
main.learning_rate = 0.0012
main.dropout = 0.08
main.num_epoch = 5
```
## Used Tricks
* TF-Records
* GRU Network
* AutoGraph
* Bayesian Opimization
## Results
### Confusion matrix
![Conmat](https://github.com/LEGO999/Human-Activaity-Recognition-HAPT/blob/master/ConMat.PNG)  
Final accuracy on test set: 92.4%.
### Visualization
For two random segments:
![visual1](https://github.com/LEGO999/Human-Activaity-Recognition-HAPT/blob/master/visualization/20200211-112221.png)
![visual2](https://github.com/LEGO999/Human-Activaity-Recognition-HAPT/blob/master/visualization/20200210-213757.png)
## Authors
- CAO Shijia, https://github.com/scarlettcao
- ZHONG Liangyu, https://github.com/LEGO999
