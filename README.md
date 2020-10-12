# Drug-sensitivity-prediction
User need to save input RNA-seq, target drug response files and embedded matrix in the same folder. Name of input gene expression file is **RNASeq_log.csv** and drug response file is **Drug_AUC.csv** in all the codes. <br/>
**Drug_AUC.csv:** https://drive.google.com/file/d/13JRk93txHasTZLKocL9eBrjaui1fNPpm/view?usp=sharing,%20 <br/>
**RNASeq_log.csv:** https://drive.google.com/file/d/1fsEi3ILyyEQMgOWFlWH7HMVCzd0ddoDu/view?usp=sharing

## Required Python packages
- Numpy
- Pandas
- sklearn
- PyTorch

## **nn_base.py**
A deep neural network that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. This code selects top 100 features based on correlation coefficient between genes and target drug response which can be changed by modifying the variable **_N_input_**.

## **nn_coexp.py**
A deep neural network that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. This code selects top 100 features based on correlation coefficient between genes and target drug response which can be changed by modifying the variable **_N_input_**. It uses the co-expression matrix of that 100 genes to introduce network information into the prediction.  
### **Framework**
![Image description](https://github.com/compbiolabucf/Drug-sensitivity-prediction/blob/master/Framework_nn_coexp.jpg)

## **nn_embed.py**
A deep neural network that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. It uses an embedding matrix build from local neighborhood structure to introduce network information into the prediction. This code selects top 50 features from each of gene expression and embedding matrix based on correlation coefficient between genes and target drug response and concatenate them. Number of features can be changed by modifying the variable **_N_input_**. 
### **Framework**
![Image description](https://github.com/compbiolabucf/Drug-sensitivity-prediction/blob/master/Framework_nn_embed.png)

## **E_net.py** 

The code for Elastic net regressor that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. The variable **_FS_** sets the feature selection scheme where 0 indicates correlation based feature selection and 1 indicates network based feature selection. This code selects top 100 features in either cases which can be changed by modifying the variable **_cutoff_**. It is implemented via Python package
sklearn.linear_model (ElasticNet). 

## **PLSR.py** 

The code for Partial least squares regressor that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. The variable **_FS_** sets the feature selection scheme where 0 indicates correlation based feature selection and 1 indicates network based feature selection. This code selects top 100 features in either cases which can be changed by modifying the variable **_cutoff_**. It is implemented via Python package sklearn.cross_decomposition (PLSRegression).. 

## **RF.py** 

The code for Random forest regressor that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. The variable **_FS_** sets the feature selection scheme where 0 indicates correlation based feature selection and 1 indicates network based feature selection. This code selects top 100 features in either cases which can be changed by modifying the variable **_cutoff_**. It is implemented via Python package
sklearn.ensemble (RandomForestClassifier).

## **SVR.py** 
The code for Support vector machine that takes gene expression as input, predict drug response in terms of AUC and finally gives the correlation coefficient between the predicted AUC and actual AUC as output. User needs to specify the path to the folder where the input and target files are saved at the beginning of the code to the variable **_path_**. The variable **_FS_** sets the feature selection scheme where 0 indicates correlation based feature selection and 1 indicates network based feature selection. This code selects top 100 features in either cases which can be changed by modifying the variable **_cutoff_**. It is implemented via Python package
sklearn.svm (SVR).

Please send any email request to Dr. Taehyun Hwang (hwangt@ccf.org) to access the RNA-seq and drug response datasets.
