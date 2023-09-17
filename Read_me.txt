Hi, Here is my submission code.

The files should be executed in following order.

1. Data Preprocessing.ipynb
2. NN_Fault_Detection.ipynb

The first code generates the data needed for the NN model, including: 
	- Features.npy
	- Features_fine.npy
 	- Features_val.npy
	- Target.npy
	- Target_fine.npy

The first code ran on my local CPU. In the attached environment (env_sub9.yaml). I assume that you have unpacked the given data as follows: 
Train files: \imgs_2023050915314323740\train_test_dataset_Fault Impact Analysis\ ( all train csv files)
Val Files: \validation_clean\ (validation csv files)

The Features files contain following features:
Z-score normalized features at time t-1: access_success_rate, ressource_utilition_rate, TA, bler, cqi, mcs, data_rate
the hour before the fault occured encoded with one-hot-encoder. 
Z-score normalized difference of the features at t-1 and t-2. ( here I made an error when calculating this feature for the validation data and the fine tuning data -> I calculated F[t] - F[t-1] instead of F[t-1] - F[t-2].)


After that the data contained in Data_diff.zip was created, zip file for google colab

The second part, NN_Fault_Detection.ipyn ran in google colab with a GPU. 

Simply load in the data from [1] and then proceed. For the code to run, you need to unzip the Data_diff.zip.

As a loss function I used the F1-score (made differnatiable)

Additionaly, I oversampled the fine tune data (where the fault occures by a factor of 8). 






