# RESULTS

I took **_"SSD Resnet50 V1 FPN 640X640"_** as base model and trained the model with 15 cell images. Training process took place by running Tensorflow Object Detection API on Google Colab.

I trained the model for 10200 steps and loss was under same level (0.3) constantly. So I stopped the the training process and I skipped to testing process. 
(_Since the checkpoints are stored in a Google Drive folder, if desired, model training can be continued from where it left off._)

The loss value during training can be seen in the graph below : 

![tensorboard](https://user-images.githubusercontent.com/74496005/149842236-8342ed81-90ba-41d1-9161-e2a0af44f2fb.JPG)

---

When I tested the model, I observed it didn't detect more than 100 cell. According to TensorFlow [website](https://www.tensorflow.org/lite/tutorials/model_maker_object_detection) TF Lite models have maximum 25 detections, TensorFlow model outputs maximum 100 detections.  Therefore I followed these steps :

- I divide the test images into 2 equal parts (1500 x 750).
- I applied the model on each half picture.
- I saved the corner points of detection boxes into corresponding csv files.
- Using these points, I circled the cells in each half image.
- Finally, I combined these images and write the detected cell number in the upper left corner.

An example image shows these steps : _(Top image is the original result produced by the model. Below image is the final result after processes.)_
![example_of_steps (1)](https://user-images.githubusercontent.com/74496005/149845754-98a14730-93ae-4cad-a5a1-2739843cf1b4.jpg)

---
There is a  part in image testing code : 

`min_score_thresh=.25`

This value affects how many objects we can detect. The smaller this value, the more objects we can detect, but the higher the possibility of false detections.


For example I used the same model with 0.20 and 0.25 threshold value and I obtained the following results : 
_(I also labeled test images with LabelImg tool. In this way I could find the real cell number )_

|  IMAGE   | Real Cell Number | Detected Cell (0.25 Threshold)|Detected Cell (0.20 Threshold) | Accuracy(0.25)|Accuracy(0.20)|
|----------|------------------| ------------------------------|----------------------------- |---------------|--------------|
|Image_016 |  199|158|174|79%|87%|
|Image_017 |  155|120|132|77%|85%|
|Image_018 |  187|155|172|82%|92%|
|Image_019 |  171|137|153|80%|89%|
|Image_020 |  171|126|149|73%|87%|
|Average||||78%|88%|
##### _All test images and their results can be seen **test_images_result** folder in this directory._
##### _(NeurologIQ_Solution/ML_Model/test_images_result )_

#

At 0.20 threshold value, I observed that there is 1 false detected cell in each _Image_016, Image_018 and Image_019._ But with that threshold value, there is 10% increase in accuracy. Therefore I think that small false detection can be ignored. The most suitable threshold value is 0.20 in this case for the used model. 

---

## Result Images for _SSD Resnet50 V1 FPN 640X640_ model with _0.20_ threshold and 10k steps Training (from Image_016 to Image_020 in order)


![Image_016-2](https://user-images.githubusercontent.com/74496005/149851820-2215258e-0ceb-457c-9b5a-e1f95e393fc6.jpg)

![Image_017-2](https://user-images.githubusercontent.com/74496005/149851832-33d86e2d-9b6f-426b-9979-f54b748cf585.jpg)

![Image_018-2](https://user-images.githubusercontent.com/74496005/149852008-781e3d16-6a6e-47a6-8957-9144f67da709.jpg)

![Image_019-2](https://user-images.githubusercontent.com/74496005/149852039-5bc6bf14-e75f-4b0b-874e-7a7e5f07f6fa.jpg)

![Image_020-2](https://user-images.githubusercontent.com/74496005/149851868-80033e5a-5d7d-43ea-b834-280cbc42367a.jpg)
