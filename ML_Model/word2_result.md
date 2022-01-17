# RESULTS

I took **_"SSD Resnet50 V1 FPN 640X640"_** as base model and trained the model with 15 cell images. Training process took place by running Tensorflow Object Detection API on Google Colab.

I trained the model for 10200 steps and loss was under same level (0.3) constantly. So I stopped the the training process and I skipped to testing process. 
(_Since the checkpoints are stored in a Google Drive folder, if desired, model training can be continued from where it left off._)

The loss value during training can be seen in the graph below : 

![tensorboard](https://user-images.githubusercontent.com/74496005/149842236-8342ed81-90ba-41d1-9161-e2a0af44f2fb.JPG)
