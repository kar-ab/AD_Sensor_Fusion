# AD_Sensor_Fusion

#### this project is still in its nascent stage, so heavy changes are expected and you may find the coding might not be upto appropriate standard

For Autonomous Driving, it’s a well established fact that a single sensor cannot provide ‘all-in-one’ capabilities. Each sensor has its own drawbacks and hence fusing sensors to complement each other becomes vital. 
	
Using deep neural networks for fusing sensor information to solve complex perception tasks is still an active research quesion in Autonomous Driving. In [[1]](https://arxiv.org/pdf/1902.07830.pdf), a complete outline on different classification for sensor fusion (enlisted below), is discussed. 

#### 1. What sensors to fuse?
#### 2. How to fuse? 
#### 3. When to fuse? 

The focus of this repository to provide an example implementaion of sensor fusion. In this repository, camera and lidar are fused from KITTI dataset. Based on classififcation *when to fuse*, colab files for following types of sensor fusion is provided: 

#### 1. Early Fusion:
 
Raw data from multiple sensors are fused before any processing is carried out. Fused data are given as input to neural networks, and so, Input dimension to the neural network will be in the more than 3 dimensions, (RGB channels and fused lidar data). A network feature encoder at input creates feature map and perception taks such as object detection can be carried out in further stages. Neural networks learn form the weaknesses and strengths of each modalities and provide a final output. 

[Colab_file](./Kitti_Early_Sensor_fusion.ipynb)


#### 2. Later Fusion:

In late fusion, first decision outputs (like object detection) from each modality is combined and then provided to a neural network. One of the most common approach is to fuse bounding boxes from lidar and camera data, later achieve a final bounding box for each object in question. Since there is lots of advancement on detecting bounding boxes in lidar and camera data individually, this provides a head-start for implementing late fusion. 

[Colab_file](./Kitti_Late_Sensor_Fusion.ipynb)


## References:

1. [Deep Multi-modal Object Detection and Semantic Segmentation for Autonomous Driving: Datasets, Methods, and Challenges](https://arxiv.org/pdf/1902.07830.pdf)
2. [Optimal Sensor Data Fusion Architecture for Object Detection in Adverse Weather Conditions](https://arxiv.org/pdf/1807.02323.pdf)
3. [Vision meets Robotics: The KITTI Dataset](http://www.cvlibs.net/publications/Geiger2013IJRR.pdf)

## Acknowledgement :pray:
- [KITTI Dataset Team](http://www.cvlibs.net/datasets/kitti/)
- repository https://github.com/kuixu/kitti_object_vis
- repository https://github.com/charlesq34/frustum-pointnets/blob/master/kitti/kitti_util.py
