# Master
Character Recognition and Tracking in Specific Scene of Video


#Description

An important and challenging computer vision task is object tracking in real-time videos or time-lapse image sequences [1-9]. Example applications include crowd surveillance, traffic monitoring, autonomous driving and flying, robotics, ocean and space exploration, precision surgery, and biology. In many applications, the large volume and complexity of such data make it impossible for humans to perform accurate, complete, efficient, and reproducible recognition and analysis of the relevant information in the data.

There are three fundamental steps in object tracking: object detection/segmentation in each frame of the video, object linking from frame to frame in order to obtain the trajectories, and object motion analysis from the trajectories. The difficulty in many applications is that objects may enter or leave the scene, touch/occlude each other, have similar appearance, and change appearance over time due to illumination changes, scale and shape changes, and deformations, making it hard to keep track of their unique identity. Therefore, object tracking is still a highly active research area in computer vision.

The goal of this group project is to develop and evaluate a method for tracking pedestrians and analysing their motion in real-world video recordings. Many traditional and/or machine or deep learning-based computer vision methods could be used for this. You are challenged create and implement your own tracking method and evaluate its performance on a public dataset from a recent international benchmarking study.

#Tasks

The group project consists of three tasks described below, each of which needs to be completed as a group and will be evaluated for the whole group.

Public Dataset

The dataset to be used in the group project is from the Segmenting and Tracking Every Pixel (STEP) benchmark and consists of two training videos and two test videos. It is part of the long-standing Multiple Object Tracking (MOT) benchmark and provides annotations where every pixel has a semantic label and all pixels belonging to the most salient object class (pedestrian) have a unique tracking ID. The benchmark is part of the STEP-Workshop organised at the 2021 International Conference on Computer Vision (ICCV).

The dataset including the annotation labels and further information can be found here:
https://motchallenge.net/data/STEP-ICCV21/

The two training videos with corresponding annotations can be used to learn more about the data and (if you are using machine/deep learning) to train your method. For testing, you are required to demonstrate your method on the first test video. You are welcome to also demonstrate it on the second test video, but this is not required (it is a more difficult case).

Task 1: Track Pedestrians

Develop a Python program to track all pedestrians in the videos. Specifically, the program must perform the following subtasks:
1.1 Detect all pedestrians in all frames and calculate the bounding box for each of them. It is not necessary to perform pedestrian segmentation (though you are welcome to try). Notice this means the annotations (labels) of the training set provide more information (pixel-level) than needed for this project (object-level). To get training data for the detection task, you need to convert the pixel-label maps to bounding boxes.
1.2 Link the bounding boxes over time to obtain the trajectory for each pedestrian. This means identifying which detections in two successive frames of the video belong to the same pedestrian. Criteria for this can be based on distances between the boxes or features calculated from the pixel values within the boxes.
1.3 Draw the bounding box and corresponding trajectory for each pedestrian. That is, for each video frame, the program must show for each pedestrian in that frame its box at that time point and its trajectory up to that time point. Use a unique colour per pedestrian to draw the box and trajectory. The trajectory can be drawn for example as a piecewise linear curve connecting the centre positions of the corresponding boxes, from the time when the pedestrian first appeared up to the current time point.

Task 2: Count Pedestrians

Extend the program so that it can count the number of pedestrians over time. Specifically, the program must perform the following subtasks:
2.1 Report the total count of all unique pedestrians detected since the start of the video.
2.2 Report the total count of pedestrians present in the current video frame.
2.3 Allow the user to manually draw a rectangular region within the video window.
2.4 Report the total count of pedestrians who are currently within that region.
The counts can be reported by printing them to the terminal or (better) directly on the video frame (for example in one of the corners of the window).

Task 3: Analyse Pedestrians

Further extend the program so that it can analyse the behaviour of pedestrians over time. Specifically, the program must perform the following subtasks:
3.1 Report how many pedestrians walk in groups and how many walk alone. Define a criterion to determines this from the bounding boxes.
3.2 Show occurrences of group formation and group destruction. A group formation event is when two or more pedestrians meet (get close) and stay together for more than one frame. A group destruction event is when at least one member of a group leaves.
3.3 Show occurrences of pedestrians entering or leaving the scene. For this subtask and the previous, use your creativity in automatically highlighting (drawing the observer’s visual attention to) these events in the video.
