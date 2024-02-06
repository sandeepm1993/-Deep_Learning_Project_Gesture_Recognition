# Deep Learning Gesture Recognition for Smart TVs

## Problem Statement

In the rapidly evolving landscape of home electronics, enhancing user experience through innovative features is paramount. This project focuses on developing a gesture recognition feature for smart TVs, allowing users to control their TVs without the need for a remote. The system utilizes a webcam mounted on the TV to monitor and recognize five distinct gestures, each corresponding to a specific command:

- **Thumbs up:** Increase the volume
- **Thumbs down:** Decrease the volume
- **Left swipe:** Jump backwards 10 seconds
- **Right swipe:** Jump forward 10 seconds
- **Stop:** Pause the movie

Each gesture is represented by a video consisting of a sequence of 30 frames.

## Dataset

The training dataset comprises several hundred videos categorized into one of the five classes. Each video, typically lasting 2-3 seconds, is split into a sequence of 30 frames. These videos are recorded by various individuals performing the gestures in front of a webcam, mirroring the intended real-world application with a smart TV.

The dataset is organized into a zip file containing 'train' and 'val' folders, each accompanied by a CSV file detailing the video classifications. Videos are stored in subfolders, with each subfolder representing a single video gesture sequence.

Notably, the videos feature two resolutions—360x360 or 120x160—necessitating preprocessing steps to standardize the input data.

## Architectures

### 1. 3D Convolutional Network (Conv3D)

3D Convolutional Networks extend the familiar 2D convolutional operations by incorporating time (or depth) as a third dimension, allowing for the analysis of video data. In this architecture, a video is processed as a sequence of images, with a 3D convolutional filter applied across the spatial and temporal dimensions to extract features relevant for gesture recognition.

### 2. CNN-RNN Architecture

This approach combines Convolutional Neural Networks (CNNs) and Recurrent Neural Networks (RNNs). The CNN component extracts a feature vector for each frame in the video, which are then processed sequentially by the RNN to capture temporal dynamics, culminating in a gesture classification based on the entire sequence.

## Understanding Generators

Data generators are crucial for managing memory usage and ensuring efficient data processing during training. In this project, custom generators are developed to handle video data, performing essential preprocessing tasks such as cropping, resizing, and normalization in batches.

## Project Goals

- **Generator:** Implement a data generator capable of preprocessing and supplying batches of video data for training without errors.
- **Model:** Design and train a neural network model that is not only accurate in gesture recognition but also efficient in terms of the number of parameters, to ensure quick inference times.

## Implementation Details

### Preprocessing

Preprocessing steps include:

- **Selecting a fixed number of frames per video:** To standardize input and reduce computational load.
- **Cropping:** To focus on the region of interest within each frame.
- **Resizing:** To standardize the dimensions of input frames.
- **Normalizing:** To scale pixel values for optimal neural network performance.

### Model Development

Two models will be experimented with:

1. **3D Convolutional Network:** For capturing spatial and temporal features.
2. **CNN-RNN Stack:** For extracting spatial features followed by temporal sequencing.

## Conclusion

This project aims to harness the power of deep learning for creating an intuitive and immersive user experience for smart TV users, demonstrating the potential of gesture recognition technology in enhancing everyday interactions with technology.
