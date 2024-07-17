# SURGE_IITK

3D Neurological Gait Recognition
Report by Naman Sharma(2430097)
Under Prof. Koteswar Rao J
Indian Institute of Technology Kanpur
SURGE 2024
Abstract
 
The pattern of limb movements and behavioral tendencies of a person while walking is well-known as a person’s gait, which can be affected due to a medical condition. Persons suffering from neurological disorders often exhibit aberrations in their gait characteristics. These aberrations may involve involuntary movements, pose habits, irregular joint motion, and so on. In this project, we aim to recognize parkinsonian, diplegic, and hemiplegic gaits specifically. These gait abnormalities occur due to Parkinson’s disease, Diplegia, and Hemiplegia, respectively. 
We capture 3D human pose patterns across frames to build a video-level hand-crafted feature set. We design this feature set while considering different aberrations caused by neurological disorders. This helps us build a machine learning solution that can recognize these abnormal gaits individually and together.

Introduction

The human nervous system is intricate, relaying electrochemical signals throughout the body to generate both voluntary and involuntary responses. Neurological disorders disrupt this system, causing visible abnormalities like erratic motor movements, speech impediments, and gait issues. 
This project aims to detect three specific abnormal gaits—Parkinsonian, Hemiplegic, and Diplegic—using automation to aid in diagnosing these disorders. By automating gait analysis through video-based 3D feature extraction, the process becomes faster, cheaper, and more consistent than traditional visual inspections. 
We extract 17 crucial skeletal points from 33 landmarks, capturing features at the frame level and applying mean and standard deviation operations across video frames. This results in 328 features per video, enhancing diagnostic accuracy. 
This approach leverages computer vision to distinguish abnormal gaits from stable ones, improving upon 2D joint estimation methods with a 3D perspective. The NeuroSynGait dataset is used to center and analyze subjects’ gaits, extracting 3D joint coordinates to build a comprehensive feature set for detecting neurological disorders. 
Extending Goyal et al.’s 2D method to 3D aims to enhance accuracy and reliability in diagnosing neurological conditions.


Research Objectives

The present study investigates the following objectives:

1.  Develop a 3D gait analysis method to detect neurological disorders using skeletal features.
2.  To Compare the performance of the proposed 3D feature set with existing 2D methods using the body features.






Frameworks & Body Coordinates
 

We use three types of frameworks to extract skeletal features:
	MediaPipe: A framework for building perception pipelines, using a two-step detector-tracker to predict 33 3D pose landmarks from video frames, enabling efficient skeletal point extraction.

	3D CNN: 3D Convolutional Neural Networks capture motion and spatial features from video data by extending 2D convolutions into the temporal domain, enhancing classification accuracy for video analysis tasks.

	AlphaPose: A top human pose estimation framework using a Regional Multi-Person Pose Estimation method, combining a spatial transformer network and single-person pose estimator for precise multi-person pose estimation. 

We used mediapipe, but the previous paper used old and that were less efficient and produced lesser accuracy


Datasets & Conditions for Feature Extraction
 

	We used the self-crafted NeuroSynGait video dataset, created by imitating different gaits. 

	The model was trained on 164 body features extracted on a frame-wise basis from each video.

   

	The NeuroSynGait Dataset contains over 400 videos, 100 each for Diplegia, Hemiplegia, Parkinson’s, and Normal gait. Sample:

 
Results and Discussion
 

•	Cross-Validation Accuracy: Our model achieved a maximum accuracy of 84.6% with Random Forests, surpassing conventional methods. The average cross-validation accuracy across models was 74.7%, highlighting the robustness of our feature set.

•	Test Accuracy: Our model outperformed others with a top accuracy of 92.3%, demonstrating its effectiveness in real-world scenarios.



     

•	Single Abnormality Detection:
	Parkinson’s Disease: Achieved 100% accuracy in both cross-validation and test datasets.
	Hemiplegia: Showed 93% accuracy in cross-validation and 100% in the test dataset.
	Diplegia: Achieved 94.2% accuracy in cross-validation, with superior results using raw 3D skeletal data in testing.

•	Dimensionality Reduction and Oversampling: 
Using PCA for dimensionality reduction and oversampling techniques enhanced model performance, improving both cross-validation and test accuracies.

Framework	Tree	SVM	SGD	Random Forest	Neural Network	Performances Averages
AlphaPose	0.591	0.470	0.515	0.576	0.432	0.510
3D-CNN	0.379	0.455	0.530	0.485	0.591	0.414
Mediapipe	0.712	0.812	0.734	0.766	0.904	0.808


Conclusions

•	3D Gait Superiority: 
The 3D gait feature set significantly outperforms the 2D set in detecting multiple and single gait abnormalities across various neurological disorders.

•	High Detection Accuracy: The system achieved high accuracy rates, particularly for Parkinson’s disease (100%), Hemiplegia (over 90%), and Diplegia (over 90%).

•	Improved Multi-Class Detection: The system performs better in detecting specific gait abnormalities in a multi-class setting compared to detecting the absence of abnormalities.

•	Wide Applicability: The method uses 3D pose estimation from images, making it suitable for any camera or video feed for accurate abnormal gait detection.

What is already known about this subject?

•	Previous methods have used sensor-based and visually guided approaches to analyse gait, including the use of multi-colored tracksuits and pose descriptors for joint information and gait length measures.

•	Tran et al. employed deep 3-dimensional convolutional networks (3D-CNN) for spatiotemporal feature learning, achieving good performance in video analysis tasks.



What does this study add?

•	This study advances the field of gait-based neurological disorder detection by extending the feature set to a three-dimensional context, allowing for more accurate and detailed analysis.

•	It provides a comprehensive comparison of 2D and 3D feature sets, demonstrating the superior performance of 3D features in identifying gait abnormalities.

References

•	Daksh Goyal, Koteswar Rao Jerripothula, and Ankush Mittal. Detection of gait abnormalities caused by neurological disorders, 2020.
•	Hao-Shu Fang, Shuqin Xie, Yu-Wing Tai, and Cewu Lu. RMPE: Regional multi-person pose estimation. In ICCV, 2017.
•	Du Tran, Lubomir Bourdev, Rob Fergus, Lorenzo Torresani, and Manohar Paluri. Learning spatiotemporal features with 3D convolutional networks.
•	Xingyi Zhou, Qixing Huang, Xiao Sun, Xiangyang Xue, and Yichen Wei. Weakly-supervised transfer for 3D human pose estimation in the wild. CoRR, abs/1704.02447, 2017.
•	Matthias Dantone, Juergen Gall, Christian Leistner, and Luc Van Gool. In 2013 IEEE Conference on Computer Vision and Pattern Recognition, pages 3041–3048, 2013.

