Rishub Kumar 704423827
Patrick Deshpande 604419345
 
# Brain Lesion Segmentation Introduction

Stroke and brain tumors are among the first five leading causes of death in America. Accurate detection of stroke/tumors is critical when treating these conditions. By having a lot of information about the brain tissue and what differentiates one from another, researches would be able to study brain pathology more precisely, and thus more accurately diagnose any problems.

Brain Lesion Segmentation is essentially finding effective ways of using multi-modality image parameters to align images of brain tissues and compare them. By comparing contrasting images, it is possible to use different algorithms to determine the similarity of the images. With image signatures of healthy brain tissue, the next step is to have a set of lesion definitions that can characterize the image signatures of lesions and determine if they really do differ from the healthy brain tissue.

By using different methods of statistics to look at the lesion distribution as well as account for false positives, we can attempt to minimize any error as much as possible. However, due to all the different factors that come with brain lesions, it can be very difficult to find an algorithm that does this with minimal error. These include the variability in many characteristics of the lesions like complexity of the location, size, shape, and texture. 

There are some challenges in attempting to segment brain lesions. Analyzing 3D medical scans are computationally expensive, and normal machine learning techniques take too long to train the model. It is hard to form segmentation rules for the three dimensional images because of the heterogeneous appearance of lesions, and the variability in location, size, and shape. Of course, it is possible to have a human manually trace out the brain lesions in the medical scans. However, this is not practical because it takes too long and is too expensive, rendering the manual way ineffective for large studies. In order to analyze brain scans for large studies, it is imperative to develop an automated way to segment brain lesions.

One of the state of the art tools for segmenting brain lesions is DeepMedic. DeepMedic is developed by BioMedIA, and uses a 3D Deep Convolutional Neural Network to solve segmentation tasks like analyzing injuries, tumors, and stroke lesions. DeepMedic provides an efficient training scheme using dense training on sampled image partitions. This allows it to train the network in fewer passes than traditional models. DeepMedic utilizes deeper 3D Convolutional Networks by exploiting small kernels to train the network. Parallel convolutional pathways allow for multi-scale processing that incorporates local and contextual information, and improves results. These pathways eliminate the need to load most of the large 3D volume of the medical scan into memory, and the first pathway can retain high resolution details. The final result is an output image that segments any brain lesions DeepMedic finds into easily identifiable sections.
 
 
 
References
 
Shen, Dinggang, and Zhiqiang Lao. "Brain Lesion Segmentation." SBIA - Brain Lesion Segmentation. July 2002
 
Nabizadeh, Nooshin. "Automated Brain Lesion Detection and Segmentation Using Magnetic Resonance Images." Scholarly Repository. 4 May 2015
 
Kamnitsas, Konstantinos. “Efficient multi-scale 3D CNN with fully connected CRF for accurate brain lesion segmentation”. Science Direct. February 2017
 
 
