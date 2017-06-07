# BrainSegmentation
CS188 Project by Rishub Kumar and Patrick Deshpande

Brain lesions are abnormal tissue in/on brain tissue. We have refined a program (using the pix2pix tensorflow library) that will highlight brain lesions given a png image of a brain. This program will help automate the tedious task of manually highlighting brain lesions, and strives to perform just as well as a human operator.

<img src="pics/2_IM-0001-0016-0001.dcm.png" width="900px"/>

The left side of this picture is an example of what we want to output, given the image on the right side.

# Instructions for running our project

1) Download and unzip project folder from <a href = "https://ucla.box.com/s/nwk3io3hbf8yi8n20wult32qqlcnjusv">this link</a>.

2) ONLY NECESSARY IF TEST FOLDER HAS DICOM IMAGES: If your test folder contains dicom images, run this command to create a new folder with png versions of those images (Copy the test folder into this directory first)

```sh
python mritopng.py -f <folder_with_dicom> <output_png_dir>
```

3) Now, we have a directory of png images that we want to highlight the lesions in. To do so, run the command:

```sh
./run.sh <input_png_dir>
```

If you performed step two, output_png_dir = input_png_dir. Otherwise, input_png_dir is the folder of png images you want to highlight.

Note that you may need to add permissions to run.sh

This command will open a web browser that shows the original image and our output image side by side.

If no browser is available, navigate to the c_test/images folder, and open the images in whatever image viewer you desire.

# Using Example Test Folder

```sh
./run.sh test_pictures
```
This will run the test on our training data using some pictures we have provided.

Click <a href="c_test/index.html">here</a> to see what the output of that test looks like

# Sources

We used the pix2pix tensorflow library to implement this functionality. You can find out more about this library <a href = "https://affinelayer.com/pix2pix/">here</a>, and view the source <a href = "https://github.com/affinelayer/pix2pix-tensorflow">here</a>.

The library uses conditional adversarial networks as a general purpose solution to image-image translations. You can find out more about it <a href = "https://arxiv.org/pdf/1611.07004v1.pdf">here</a>.
