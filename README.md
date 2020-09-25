# Segmentation-of-satellite-imagery

A project for the company Satellogic. 

The goal of the project to construct a machine learning model to perform segmentation on data obtained from satellites that contains static and dynamic airplanes. The model is supposed to detect and construct segmentation boxes around all planes in the images.

![43](https://user-images.githubusercontent.com/35766943/94219188-24187980-fede-11ea-82ca-0f344b1e0f81.png)

The project was completed using TensorFlow Object Detection API to build a YOLO (You Only Look Once) model. 

200 hundred images were manullay annotated using labelim (https://github.com/wangxianrui/labelImage). This generated XML files of the coordinates of the boxes on each image. The XML files were converted into CSV files and then into TensorFlow's TFrecord.

The configurations files were imported from TensorFlow and were used to train a model of 10 layers. The model was trained with the labeled dataset which took 5 hours and provided a loss of 1.75. The model was tested on 50 images and the metric used to evaluate the model was Jaccard score. The model achieved an average Jaccard score of 85%.

![output_img](https://user-images.githubusercontent.com/35766943/94220577-2af4bb80-fee1-11ea-83b2-2f7280bf9985.png)



