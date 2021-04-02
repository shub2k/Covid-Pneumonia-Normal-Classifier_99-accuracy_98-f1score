# Covid-Pneumonia-Normal-Classifier_99-accuracy_98-f1score
This repossitory contains a deep learning model to predict  if a patient is suffering from covid or pneumonia or the person doesn't suffer from any of those disease using there chest X ray ,  I have used classical transfer learning method with  a state of the art pretrained model ( resnet200d ) as a backbone and fine tuned its final layers with some heacvy augmentaions . The model shows some excellent results with a 98% f1 score and 99% accuracy in a completely hidden dataset and for the convienence i have added grad cam so that we can see what model is seeing to predict . 

# Model 
The model backbone used here is resnet200d which has been used from timm repository <a href="https://github.com/rwightman/pytorch-image-models">timm pytorch models repository </a>, A bit about about why resent200d and why not other architectures like efficient nets , nfnets , vgg etc , resnet200d is supposed to perform better for xrays images and effnets and other perform poor for xrays images although i tried all the other architectures that i could possibly try and came to the coclusion that resnet200d indeed is the king for the backbone of my model the final layers are just Linear layers to classify into 3 categories i.e Covid , pneumonia and normal using crossentropyloss as loss function . I have used ptyorch as i find it more flexible and it suits my working type . 

# Metric used 
Model performance has been calculated using following metrics .

accuracy = 0.9909968262193147 , f1_score = 0.9801513517345098 , precision = 0.9891503234296438 , recall = 0.9722867684680466

# Datasets [ Citations / Credits ]
Train dataset :- 
The model is trained nd validated from these 3 datasets by stratifing the folds into 5 splits , the model is trained and validated using single fold and still perform excellent thanks to the datasets authors for providing these datasets
<a href="https://www.kaggle.com/tawsifurrahman/covid19-radiography-database">Train dataset 1 </a> ,
<a href="https://www.kaggle.com/bachrr/covid-chest-xray">Train dataset 2 </a> , 
<a href="https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia">Train dataset 3 </a>

Test dataset:-
The model is tested from these 3 datasets 
<a href="https://www.kaggle.com/nabeelsajid917/covid-19-x-ray-10000-images">Test dataset 1 </a> , 
<a href="https://www.kaggle.com/khoongweihao/covid19-xray-dataset-train-test-sets">Test dataset 2 </a> ,
<a href="https://www.kaggle.com/tawsifurrahman/covid19-radiography-database">Test dataset 3 </a>
