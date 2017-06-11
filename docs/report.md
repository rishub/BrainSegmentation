Rishub Kumar 704423827
Patrick Deshpande 604419345
 
# Brain Lesion Segmentation Final Report
 
Methods 
 
To gather our data, we went to the lab in the Neuroscience building and looked at Brain MRI scans for many patients. There were over a hundred patients, each with about 25 pictures all from different angles. We eliminated some of the images that didn’t really show the brain as much and were mostly the jaw/face area. We also ignored patients whose scans contained a lot of noise or whose scans did not really contain any lesions. We wanted pictures that really showed the lesions and had a lot more bright spots so that there was some contrast in the color, and our program would be able to learn. After choosing the patients and pictures, we had about 100 pictures from 12 patients. Then, we simply had to go through all the images and manually select the areas with lesions. With this we were able to export the images so that we have not only the original images, but also the corresponding images, with the lesion spots in white and the rest of the scan in black. These essentially become our input and target images.
 
To actually train a model on these images, we used python and tensorflow with the tensorflow pix2pix library. To prepare our data to be trained on the model, we first needed to convert the .dicom mri scans to .png’s. We easily did this with a python script converter that we found online. Once we had the images in png form, we were able to separate the input images and target images into different folders. Using the pix2pix library, we then stitched these pics together in order to achieve something like the picture below.
 

 
With this, we then separated our stitched pictures into 2 folders, training data and testing data. We were then able to train our data specifying that we wanted it to train from B to A. This means the the input image is B, the right half in our stitched image, and the target is A, the left half. To train our model, it took about 12 hours, and we basically ran it over night. Now, the model is ready to test.
Evaluation
 
After training our model, we wanted to test its ability to recognize brain lesions in images it hasn’t seen before. It is important to test our model with images the program hasn’t seen in testing because it has already learned what the output for that image is supposed to look like, and does not provide a meaningful way to test the accuracy of our program. We made sure to withhold images from each individual in the training stage.
 
When evaluating the effectiveness of our model at recognizing brain lesions, we had to take a few characteristics into consideration. First, we would prefer that our model produces false positives over false negatives. In other words, we would prefer labeling normal brain tissue as a lesion instead of failing to label abnormal tissue. This ensures that potentially dangerous lesions are recognized more frequently. Second, we must be able to analyze images in a timely fashion. Digital medical scans are large files, and our program needs to be able to evaluate images quickly to be practical.
 
Results 
 
After testing our training mode the images we saved for testing, we got these results.
 
Let’s analyze our results in the context of our evaluation characteristics. First, we prefer false positives over false negatives. Out of the 9 images we used for testing, (maybe) only one small lesion wasn’t recognized by our program. In most of the images, the output lesion segments zones are larger than the input images, which is desired. However, we clearly need to test our program on more images to truly verify this requirement. Since we weren’t working with that much data, we preferred to have a majority of our images used in the training of the model. Second, our program analyzed these 9 images in under a minute. This is very reasonable for the complexity of our program and the value it provides.
 
Discussion 
 
Let’s look at some big picture takeaways from this project. One of the major problems with our program is that training the model takes a very long time. Training 60 images (256 x 256) took around 9 hours. Using more images to train the model would result in more accurate results, but also would increase the time required to train it. Furthermore, it becomes very difficult to tweak the model because of the time investment needed to evaluate these results.
 
Despite the long time required to train the model, it is clear that the results are useful and meet our evaluation criteria. Despite only training our model on 60 images, we are still able to quickly recognize brain lesions, and recognize every lesion in the original images.
 
 
 
Sources
 
See our project (including download source code) here: http://rishub.com/BrainSegmentation/
 
Hesse, Christopher. Pix2pix Library. https://github.com/affinelayer/pix2pix-tensorflow
 
Isola, Phillip. Image-to-Image Translation with Conditional Adversarial Networks. 21 Nov. 2016. https://arxiv.org/pdf/1611.07004v1.pdf
 
Mujeeb, Danish. Dicom to png. https://github.com/danishm/dicom-to-png
