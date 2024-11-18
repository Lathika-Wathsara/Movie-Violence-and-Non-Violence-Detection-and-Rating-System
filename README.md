# Movie-Violence-and-Non-Violence-Detection-and-Rating-System


This repository contains a system designed to detect and classify violent content in movies. The module leverages advanced machine learning and image processing techniques to analyze video clips and audio data, classifying violent scenes into specific categories.

---

## Features
- *Multi-class Classification*: Detects specific types of violent scenes such as fights, explosions, accidents, and more.
- *Audio-Video Analysis*: Combines audio and video analysis to improve detection accuracy.
- *Blood Detection Module*: Identifies and classifies the severity of blood presence in scenes.
- *Custom Datasets*: Built on custom datasets derived from movie clips and publicly available datasets.

---

## System Workflow

1. *Video Preprocessing*:
    - Splits a movie into 10-second clips.
    - Extracts frames and audio from each clip.

2. *Audio Analysis*:
    - Uses *VGGish* to extract features from audio clips.  
      > *VGGish* is a pre-trained audio embedding model based on the VGG architecture. It maps audio input into 128-dimensional embeddings designed to capture essential features for downstream tasks like classification.

    - Generates probability scores for violent content from audio data.

3. *Video Analysis*:
    - Initially tested with CNN models like InceptionV3, ResNet, and VGG16, but these approaches did not yield optimal results for violent scene detection.
    - Implemented the *MovieNet* model, which provided better performance for video-based violence detection.  
      > *MovieNet* is a model specifically designed for video content analysis, leveraging spatiotemporal information from movies to improve classification accuracy.

    - Applies a transformer encoder-based classifier to assign probabilities for different violent classes.

4. *Blood Detection*:
    - Identifies blood in frames using a separate blood detection module.
    - Dynamically classifies the severity as minor, moderate, or severe.

5. *Final Severity Score*:
    - Combines scores from audio, video, and blood detection modules to generate a comprehensive violence severity score.

---

## System Flow Diagram

Below is the high-level flow diagram of the Violence Content Detection System:

![System Flow Diagram](path/to/your/flow_diagram.png)

> Replace path/to/your/flow_diagram.png with the relative path to your flow diagram image in the repository.

---

## Datasets

The module uses the following datasets:

1. *Multi-class Violent Dataset*  
   - Contains movie clips from 6 violent classes derived from XD-Violence dataset definitions and 1 non-violent class.  

2. *Blood Detection Dataset*  
   - Contains 2 classes: blood and non-blood.  
   - Includes images of red-colored objects to improve robustness.  
   - [Download Blood Detection Dataset](link-to-dataset)

> Replace link-to-dataset with the actual dataset links.

---

## Installation

### Prerequisites
- Python 3.8 or later
- TensorFlow 2.7
- Keras
- MoviePy
- FFmpeg
- Scikit-learn
- OpenCV
