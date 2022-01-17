Kesinlikle USAGE KISMI OLSUN
Project Architecture - Kesinlikle olsun. Çünkü 1,....6 kısmını buraya yazacam.(Buraya diyagram da ekle kesnlikle)

İlk başta gerekli dosyaları, drive'a kurmak için bir mkdir ile başlayan kod vardı, bunu bir python dosyasına yazayım. Setup diye ilk başta çalıştırayım
Readme içerisinde, bundan bahsederim ayrıca. Usage kısmında


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

