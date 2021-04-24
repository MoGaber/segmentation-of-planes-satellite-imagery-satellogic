# Segmentation-of-satellite-imagery

A project for the company Satellogic. 


![43](https://user-images.githubusercontent.com/35766943/94219188-24187980-fede-11ea-82ca-0f344b1e0f81.png)

Satellogic is an Argentine satellite company. They wanted to build a machine learning model that can perform object-detection on the images their satellite collects. I completed that project using Tensorflow API. I did the following:
- Received a dataset of 2000 images. Manually labeled the images using "labelimg" which produced xml files of the coordinates of the boxes on each image.
- I turned the xml to csv format and split it randomly into train and test
- I Generated a tf_record for the train and test files using the provided notebook by TF
- I used the mobilenet model from tensorflow which was trained on COCO dataset. TensorFlow provides various versions of the models and the tradeof between these models is the speed and accuracy, I chose this version: https://github.com/tensorflow/models/blob/master/research/slim/nets/mobilenet_v1.md
- I used the configuration file provided by the model (with a small edits to the batch size and number of classes).
- I trained the model on the data and generated a frozen input graph.
- I finally imported the model with the generated frozen input graph to test on the test dataset.
- I measured the accuracy using the mAP which is just the average intersection over union (Jaccard score). I found the score to be 85%

The evaluation metric of the model is the COCO mAP (mean average precision). mAP is the average of the IOU for the images. IOU is intersection over union. It’s the intersection of the predicted box over the intersection of the union of two boxes. As you can imagine, the larger the intersection the closer it will be to the union and then the larger the accuracy. I put a threshold of 0.5 so that if IoU>0.5 we consider that to be a correct prediction or a true positive. Then mAP is just the average



![output_img](https://user-images.githubusercontent.com/35766943/94220577-2af4bb80-fee1-11ea-83b2-2f7280bf9985.png)



