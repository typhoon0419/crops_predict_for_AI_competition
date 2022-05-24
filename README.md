# Crops Prediction for AI Competition
本專案是「農地作物現況調查影像辨識競賽 - 春季賽：AI作物影像判釋」中所使用的程式，利用我們的模型可以獲得94 %的準確率。

## Enviroments
We use python 3.8.11 to run our project, and install four packages to build our enviroment.
1. OpenCV-python 4.5.5.62  
1. Numpy 1.19.5
1. TensorFlow 2.5.0
1. Keras 2.4.3  

We have uploaded my enviroment.txt, you can use the command below to install my enviroments.  
```pip install -r enviroments.txt```  

## Data Preprocessing
We do my data processing on `01_dataProcessing.ipynb`. We have read every data in the dataset, cut data into square and resize every data to 256*256. After resize the data, the data will be save to another folders.  
You can change 
1. `data_path` to relocate the dataset
1. `cut_shape` to resize the data
1. `reshape_folder` to save data to new folder.


## Data Normalization and Training
We do normalization and training on `02_dataload.ipynb`. We read every resize data in dataset, then divide the whole dataset by `255.0` for normalization, that can keep every element is in range of 0~1. We split our dataset into **train data** and **test data**, then split **train data** into **new train data** and **validation data**.  
We sent the **new train data** and **validation data** into model for training, and **test data** for testing.  At last, we saved our model into `my_model.hdf5`.


## Predict testing dataset
We do normalization and training on `03_predict.ipynb`. First we load the models that we save after training, then load the testing dataset and do data preprocessing. Final step, predict dataset and add the results into csv file.
