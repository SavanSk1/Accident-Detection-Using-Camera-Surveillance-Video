1 Building a Dataset

We extract the Dataset from Youtube.

First thing we need to do is to download the candidate videos in order to process the images and homogenize the data. We used OpenCV library to extract the frames, and scikit-image to modify and resize them. Frames are converted to 640 pixels width and from colors to grayscale.

2 Dataset preparation

Once images are processed, starts the tough task which is to visualize and classify the images. Images should be stored manually in two folders accidents and no-accidents.

When images are allocated in the right folder, it is the time to run the next module '2_Dataset_preparation' to:

Split the supervised images in two groups, one for train and another for valid which each contains images of accidents and no-accidents. The module splits them randomly and does data augmentation of accident images (which are fewer than no-accident).

It splits in train (80% of supervised image set) and valid (20% of supervised image set) i.e. to test it.

3 Model train

We followed fastai course during the AI Saturdays. To train the model, we apply the knowledge adquired and fastai libraries. To create the model we selected ResNet-34 architecture. ResNet-34 is a pre-trained Model for PyTorch to work with the images. By using a pre-trained model we are saving time. Someone else has already spent the time and computed resources to learn a lot of features and our model will likely benefit from it.

4 Prediction

To analyze if a video have an accident, with current coding, it is required to upload a video to a folder. Then video is split to frames and processed to homogenize the images to grayscale and downscale the width to 640 pixels.

Then we load the trained model and process the images to generate a preliminar prediction. We normalize the preliminar prediction to remove false positives due to model accuracy, difficult light conditions in image or low quality, Once the preliminar prediction is normalized, we analyze it to determine if there is any accident in the video.

Note: Dataset-Train_ac_1.tar , Dataset-Train_ac_2.tar ,Dataset-Train_noac_1.tar ,Dataset-Train_noac_2.tar ,Dataset-Train_ac_3.tar ,Dataset-Valid.tar.It results in (Sorry about that, but we can’t show files that are this big right now.).You can click on view raw and save it to your system.They contain Datasets.
