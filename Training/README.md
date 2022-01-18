# Information

In TensorFlow object detection API, the model is saved in a folder. It contains ;
- **Variables** folder
- **Assets** folder
- **saved_model.pb**

saved_model.pb file holds the graph structure.

The variables folder holds learned weights.

The assets folder allow us  to add external files that may be needed.




* These folders for my model can be seen under the : **/Training/my_model/saved_model/** 
#### _(Since Assets folder is empty, it can not be loaded to Github)_

#


When I tried to save the model with .h5 extension I encountered some problems : 

- Keras has feature to save model in .h5 format. But since the model in this project is trained with TensorFlow, it can not be loaded with Keras. Therefore saving property of Keras can not be used.

- The second one ; Model can be loaded with Tensorflow. But it has no feature to save the model with .h5 extension.
