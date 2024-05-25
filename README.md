# Solar-Panel-Inspection-using-MobileNetV3-Architecture-


This is a project designed to receive the MP4 file of the output from a drone designed for solar panel inspection and gives output as a AVI file with the prediction of the physical status of the recorded solar panel.

## Working of the model

### About the dataset

* This model is trained using a labelled dataset of images from KAGGLE. Website link: https://www.kaggle.com/datasets/pythonafroz/solar-panel-images

* The Dataset has been divided into SIX classes namely,

..* 1. Clear Solar Panel
..* 2. Dust covered Solar Panel
..* 3. Snow Covered Solar Panel
..* 4. Solar Panel covered in Bird Dropping
..* 5. Solar Panel with physical Damages
..* 6. Solar Panel with Electrical Damages

*These are detectable given the condition that the reason for the decerase in efficiency in solar panel is detectable using a RGB camera*

###About the Model

* The project uses the technique called [Transfer Learning](https://www.geeksforgeeks.org/ml-introduction-to-transfer-learning/ "GeeksForGeeks") as the training dataset for solar panel is relatively small and as the model is designed to work with faster training time. 

* This Model leverages on the pre-trained model called [MobileNetV3](https://paperswithcode.com/paper/searching-for-mobilenetv3 "Papers with code") which is a CNN architecture used in devices with low computational resources and power efficiency.

* The data from the dataset is added to be assessable by the model.This is then splitted into training and testing dataset (for evaluation purposes)

* Layers have meen added to the model using keras for customizing the model to implement transfer learning for feature extraction.
... The layers are
..* Flatten
..* Dropout
..* Dense (using softmax as sctivation function)
  
* A concept of early Stopping is introduced to prevent overfitting 

* Now the model with the additional layers trains on the provided labelled Training data.

* Afer working on the model, The performance of the model is evaluated using a confusion matrix

### The Input and the Output

* Using [Tkinter module](https://youtu.be/YXPyB4XeYLA?si=gj8uqFV9J-iM83O5 "FreeCodeCamp") and [Time module](https://docs.python.org/3/library/time.html "Python Documentation") ,Input MP4 file is selected from the user's system and output is saved as an AVI file saved in the directory present in the code under the variable **output_path** in the last cell.

* The module [CV2(OpenCV)](https://www.geeksforgeeks.org/opencv-python-tutorial/ "GeeksForGeeks") is used to label the frames of the input video with the desired font and color.

* The program resizes the frames of the input into 224x224 pixels adhering to the input size of MoblieNetV3 for better prection accuracy.

* Would return a message stating **"No file Selected"** if no file is selected

# Conclusion and Result

The model performs well with highest recorded accuracy of 97.15% and an average accuracy of 94.31% in predicting the status of the Solar Panel in a frame of the input MP4 video file.

