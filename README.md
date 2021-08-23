# AD_Sensor_Fusion

For Autonomous Driving, it’s a well established fact that a single sensor cannot provide ‘all-in-one’ capabilities. Each sensor has its own drawbacks and hence fusing sensors to complement each other becomes vital. 
	
Using deep neural networks for fusing sensor information to solve complex perception tasks is still an active reserach quesion in Autonomous Driving.  A brief intoduction to the different types of sensor fusion. In [1](https://arxiv.org/pdf/1902.07830.pdf), provides a complete outline on different classification for sensor fusion: 

#### 1. What sensors to fuse?
#### 2. How to fuse? 
#### 3. When to fuse? 

The focus of this repository to provide an example implementaion of sensor fusion. In this repository, camera and lidar are fused from KITTI dataset. Based on when to fuse, colab files for following types of sensor fusion is provided: 

#### 1. Early Fusion:

 
Raw data from multiple sensors are fused before any processing is carried out. Fused data are given as input to neural networks, and so, Input dimension to the neural network will be in the more than 3 dimensions, (RGB channels and fused lidar data). A network feature encoder at input creates feature map and perception taks such as object detection can be carried out in further stages. Neural networks learn form the weaknesses and strengths of each modalities and provide a final output. 

Colab_file: 


#### 2. Later Fusion:


In late fusion, decision outputs (like object detection) from each modality is combined and then provided to a neural network. One of the most common approach is to fuse bounding boxes from lidar and camera data, later achieve a final bounding box for each object in question. Since there is lots of advancement on detecting bounding boxes in lidar and camera data individually, this provides a head-start for implementing late fusion. But if for some reason (like occluded object leading incorrect detection by one of the sensors) same object in the world is perceived as different objects in different modalities. A difference in detection raises the question as to which sensor will have higher priority of reliability. 

Colab_file: 


References: 

1. https://arxiv.org/pdf/1807.02323.pdf
2. 
























