# Deepfake Detection System
<a href = "https://github.com/adityapathakk/Deepfake-Detection-System/blob/main/documents/finalCapstoneVideo-team77.mp4">This</a>  will take you to a presentation video with a brief demonstration. To access and view the video, you will probably need to download it. Yes, it's completely safe, do not worry!

## Abstract
With the increasing prevalence of manipulated videos, deepfakes pose a significant challenge to media integrity, digital forensics, and societal trust. This project introduces a deepfake detection system leveraging hybrid deep learning techniques to address this concern. Using ResNet for spatial feature extraction and LSTM for temporal analysis, the system captures subtle anomalies in video content that are often missed by conventional methods. A comprehensive preprocessing pipeline ensures optimal input quality, focusing on extracting faces from video frames and enhancing data diversity through augmentation. The model trains on benchmark datasets such as the Deepfake Detection Challenge (DFDC), achieving high accuracy and robustness across diverse scenarios. By combining spatial and temporal inconsistencies, the project offers a scalable solution for detecting manipulations in videos, including deepfakes, splicing, and copy-move forgeries. This work underscores the potential of hybrid architectures in combating the growing threat of deepfake videos and advancing digital forensics.

Check out this <a href = "https://github.com/adityapathakk/Deepfake-Detection-System/blob/main/documents/Poster-CapstoneTeam77-ForgeryDetectionSystem.png">poster</a> that provides an overview of our project!

## What are Deepfakes?
Deepfakes are synthetic media created using artificial intelligence, where a person’s appearance, actions, or voice is convincingly altered to mislead viewers. Techniques like Generative Adversarial Networks (GANs) generate these manipulations, often blending seamlessly with authentic content. While deepfakes have applications in entertainment and education, their misuse in spreading disinformation, identity theft, and fraud has raised significant ethical and security concerns. Detecting these manipulations requires advanced methodologies capable of identifying subtle visual and temporal inconsistencies.

## Dataset Used
This project utilizes the Deepfake Detection Challenge (DFDC) dataset, curated by Facebook, which provides a diverse collection of real and fake videos. The dataset includes high-quality videos featuring various individuals under different lighting and environmental conditions.
- **Preprocessing Steps**: Each video is split into individual frames, resized to 112x112 pixels, and normalized. Faces are detected and cropped using libraries like ```face_recognition``` and ```OpenCV```, focusing on regions most susceptible to manipulation. Data augmentation techniques such as random cropping, flipping, and brightness adjustments ensure the model's robustness to variations in the dataset.
- **Dataset Split**: Videos are divided into training, validation, and testing sets to evaluate the model's generalization and accuracy. This dataset forms the backbone of training the CNN-LSTM hybrid model for detecting deepfakes.

## Methodology
<img src = "https://github.com/adityapathakk/Deepfake-Detection-System/blob/main/documents/VideoForgeryDetection-ProposedWorkFlow.png">

The deepfake detection system employs a hybrid architecture combining Convolutional Neural Networks (CNNs) and Long Short-Term Memory (LSTM) networks to analyze spatial and temporal features in videos.
### 1. Preprocessing:
  - Videos are split into frames, resized to 112x112, and normalized for uniformity.
  - Faces are detected and cropped, focusing the analysis on regions prone to manipulation.
  - Data augmentation is applied to simulate real-world variations and prevent overfitting.
### 2. Spatial Feature Extraction:
  - A pre-trained ResNet model processes each frame, extracting spatial embeddings that highlight textures, edges, and anomalies indicative of deepfake manipulations.
  - Features are passed through a ```TimeDistributed``` layer, applying the same ResNet model to each frame independently.
### 3. Temporal Dependency Modeling:
  - The sequence of spatial features from video frames is input into an LSTM layer, which captures temporal inconsistencies like unnatural transitions, jerky movements, or lighting mismatches across frames.
### 4. Classification:
  - Fully connected layers refine the learned features, with dropout layers added to prevent overfitting.
  - The final layer uses a sigmoid activation function to classify videos as real or fake based on the combined spatial and temporal analysis.

This architecture ensures that the model identifies subtle yet critical anomalies across both single frames and video sequences.

## Conclusion  
The developed deepfake detection system demonstrates the effectiveness of hybrid CNN-LSTM architectures in analyzing spatial and temporal features to identify video manipulations. By leveraging benchmark datasets and a robust preprocessing pipeline, the model achieves high accuracy, detecting even subtle inconsistencies in deepfake videos. While the system primarily focuses on offline detection, future enhancements could enable real-time analysis, integration of multi-modal data (e.g., audio-visual), and lightweight architectures for deployment in resource-constrained environments. This project contributes to the growing need for tools to counteract the misuse of deepfake technology, promoting media integrity and trust in digital content.

## Acknowledgements
Firstly, I'm grateful to the person reading this for taking their time to go through my project!<br>
I would like to extend my heartfelt gratitude to my mentors, Dr. Neeru Jindal (Associate Professor, ECED at TIET, Patiala) and Dr. Dinesh (Assistant Professor, ECED at TIET, Patiala), for their invaluable support and technical expertise throughout our venture. I'm also deeply appreciative of the faculty and staff of the Electronics and Communication Engineering Department, as well as my team members -- Rishit, Tanmay Shankar, Heeral Dhillon, and Hari Dass Sachdeva, and our friends, for their generous dedication of time and assistance in numerous ways. And of course, I'm immensely grateful to our families for their unwavering love and encouragement, always striving for our best interests with remarkable determination and sacrifice.<br>
