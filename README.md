# C-DenseUNet: 2D-3D Coupled Densely Connected UNet for Liver and Tumor Segmentation from CT Volumes. 
by [Zengming Shen](https://github.com/ALISCIFP),Bogdan Georgescu, Thomas S. Huang.

### Introduction

This repository is for the source code of  C-DenseUNet: 2D-3D Coupled Densely Connected UNet for Liver and Tumor Segmentation from CT Volumes. 
 


### Usage


1. Data preprocessing: 
   Download dataset from: [Liver Tumor Segmentation Challenge](https://drive.google.com/drive/folders/0B0vscETPGI1-Q1h1WFdEM2FHSUE).   
   Then put 131 training data with segmentation masks under "data/TrainingData/" and 70 test data under "data/TestData/".  
   Run:
   ```shell 
   python preprocessing.py 
   ```


2. Test our model:
   Download liver mask from [LiverMask](https://drive.google.com/file/d/14HxHiOKcJtpbOOvPqx-4XN7_Jrdy1Fby/view?usp=sharing) and put them in the folder: 'livermask'.   
   Download model from [Model](https://drive.google.com/file/d/1Qo4TFR4hf5wVPJSkMqGMEf4O4GjRHRyU/view?usp=sharing) and put them in the folder: 'model'.
   run:
   ```shell
   python test.py
   ```

3. Train 2D DenseUnet:
    First, you need to download the pretrained model from [ImageNet Pretrained](https://drive.google.com/file/d/1HHiPBKPw539LR0Oj5g1gD3FNRkCsxeGi/view?usp=sharing), extract it and put it in the folder 'model'.
    Then run:
   ```shell
   sh bash_train.sh
   ```

4. Train C-DenseUnet:
    Load your trained model and run   
    
   ```shell
   CUDA_VISIBLE_DEVICES='0' python train_hybrid.py -arch 3dpart
   ```

5. Train C-DenseUnet in end-to-end way:
    
   ```shell
   CUDA_VISIBLE_DEVICES='0' python train_hybrid.py -arch end2end
   ```




### Questions

Please contact 'szm0219@gmail.com'

