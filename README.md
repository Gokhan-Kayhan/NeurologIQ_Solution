# Cell Detection and Counting
## Description

This project basically consists of two parts : 

1- TensorFlow Object Detection API 

2-  Circle Drawing Around Cells and Counting

Rectangular boxes are commanly used for object detection. But in this project after the detection process, additional part was added using OpenCV and Pandas libraries. In this way, the cells are detected with bounding circle and the number of detected cells are obtained.
# 

## Project Steps

**1 - Labeling the images and make them ready for training**

I Labeled the images with "LabelImg" tool. I used only one class "cell". Then I saved the images and their corresponding XML files in train folder. More information about LabelImg can be found in its [Github](https://github.com/tzutalin/labelImg) page

**2 - Detection of the Cells**

I used TensorFlow Object Detection API to detect cells. Because it can be used on Google Colab environment and its data can be stored in Google Drive.
Also, some pretrained models can be chose from [TensorFlow 2 Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md) for transfer learning.
I got help this [Medium](https://medium.com/swlh/tensorflow-2-object-detection-api-with-google-colab-b2af171e81cc) article to run TF API on Colab.

**3 - Getting Corner Points of Detected Boxes and Saving Them**

My goal is to detect cells and enclose them with circle. Therefore, I took the corner points of detected cells and saved them in csv file. In this step, I used the codes that I saw in an [Stack Overflow](https://stackoverflow.com/questions/48915003/get-the-bounding-box-coordinates-in-the-tensorflow-object-detection-api-tutorial) question.

**4 - Calculating Center Point-Radius and Counting Total Number of Detected Cells**

Since I know the X and Y coordinates thanks to the corner points, I could calculate the values for circle. Also the length of the csv file gave me the total number of detected cells.

**5 - Showing The Cells With Bounding Circle**

I draw circles for each cell according to the calculated center points using OpenCV library. I showed total detected cell number on top left corner. Thus, I got the final images as I wanted.

#

##  Installation and Usage

* Project can be work completely in Google Colab. By executing the code blocks in the **Cell_Detection_and_Counting.ipynb** sequentially, model training and testing can be performed.
* Just some adjustments need to be made on Google Drive. The files in the **_/Colab_Documents_** folder should be used for this.

* Firstly, a folder named **_/TensorFlow_** should be created in Google Drive. Then put **_setup_folders.py_** into it. By executing `!python setup_folders.py` in Colab Notebook at Step 3 ; other necessary folders are created.

* Copy the images and their XML files from **_/Colab_Documents/train/_** and paste into **_/TensorFlow/workspace/training_demo/images/train_**

* Similarly, put any test images into **_/TensorFlow/workspace/training_demo/images/test**

* Add **_label_map.pbtxt_** which was adjusted for cell dataset, into  **_/TensorFlow/workspace/training_demo/annotations_**

* Add **_generate_tfrecord.py_** file into **_/TensorFlow/scripts/preprocessing_**

* Copy **_/Colab_Documents/ssd_resnet50_v1_fpn_640x640_coco17_tpu-8_** folder into **_TensorFlow/workspace/training_demo/pre-trained-models_**

* Add **_pipeline.config_** file which was adjusted for cell dataset, into **_TensorFlow/workspace/training_demo/models/my_ssd_resnet50_v1_fpn_**


* When all folders and files are set, the rest of the code blocks in the **Cell_Detection_and_Counting.ipynb** notebook can be executed.
