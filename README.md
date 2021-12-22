# People Detection and Social Distance Monitoring

Objective
* By delivering an AI-based system to automatically monitor and detect violations of social
distance among individuals with any given input image sizes and resolutions, this study intends
to aid in the reduction of coronavirus propagation and economic expenses. 
* In addition, the study attempts to portray a long-term heat-map of the environment based on the combination of collected people detections, movements, and steady-state individuals, and the total number of violations of the social distancing to have a complete set of information.

Video Demo: https://youtube.com/playlist?list=PL_-sHyLzrZ2N2yWD_kq3QgpdM1YEIGPGa

Model Functionalities
1. People Detection and Tracking
* Throughout the frames of a given video, the position, and state of each people of
detection, tracking, and ID assignment are updated. 
* Each people’ current state in a frame represents the horizontal and vertical location of the target bounding box (centroid), the scale (area), the aspect ratio of the bounding box sides, and the estimated values by the Kalman filter for horizontal, vertical, and bounding box centroid. 
* Such temporal information is then applied to analyze the extent of social distance violations and high-risk zones in the scenario.
2. Distance Estimation
* Inverse perspective mapping (IPM) is used by first eliminating the perspective effect on
the camera calibration. 
* Following the IPM, each person’s location in the BEV (bird’s eye view)
homogeneous space with a linear distance measurement is expected. Any two persons with a
Euclidean distance less than the set constraint in the BEV space were regarded to be contributors
to the social distancing violation. 
* Where there is a breach between two neighboring couples or
between a couple and an individual, all the detected persons involved, whether they are a couple
or not, will be assigned the red color (high-risk status). 
* On the other hand, where there is a
breach between two neighboring couples, all the detected persons involved will be assigned the
green color (safe status). Lastly, any two persons in a paired group were regarded to have the
same identity as long as they did not violate the social distancing requirements imposed on their
neighbors, in which they are depicted the yellow color (potentially risky status).
3. Crowd Map
* The crowd map depicts 2D and 3D representations of violations, such as when two big
groups of individuals were moving or remaining to be located together and violated the social
distancing rule, as well as risk heat maps in which it is applied both growing and declining
contamination rates. 
* In particular, the crowd map does not have to only be based on the current
frame, but it can also be a weighted average of all prior single-frame crowd maps. 
* The current approach, however, does not provide the most appropriate averaging weights and coefficients, nor does it ensure how to normalize the maps over time.

## Getting Started

Start by downloading the project and run "SourceCode.ipynb" file in ipython-notebook.

### Prerequisites

You need to have installed following softwares and libraries in your machine before running this project.

```
1. Python 3
2. Google Colaboratory
```

## Built With

* Keras, Tensorflow - Machine learning library
* NumPy - number python library

## Authors

* Andrew Thenedi

## Reference

* https://arxiv.org/pdf/2008.11672.pdf

## Acknowledgement

* This project is a subtopic of the Inter-departmental Final Year/Capstone Project: An Aerial Mask Detection System based on UAV.
* Supervisors: Dr. Li Boyang and Prof. Song Guo.
