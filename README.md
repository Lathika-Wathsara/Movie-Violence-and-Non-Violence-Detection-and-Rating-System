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

![System Flow Diagram]((https://github.com/Lathika-Wathsara/Movie-Violence-and-Non-Violence-Detection-and-Rating-System/blob/e07f7684e3b6f9198fac6aba9f5bdd97de577085/Flow%20diagram.jpg)



---

## Datasets

The module uses the following datasets:

1. *Multi-class Violent Dataset*  
   - Contains movie clips from 6 violent classes derived from XD-Violence dataset definitions and 1 non-violent class.
   - [Download Multi-class Violent Dataset](https://drive.google.com/drive/folders/158ceibgYDFB6q0fiuF9sjJjQCulgtK2f?usp=sharing)  

2. *Blood Detection Dataset*  
   - Contains 2 classes: blood and non-blood.  
   - Includes images of red-colored objects to improve robustness.  
   - [Download Blood Detection Dataset](https://drive.google.com/drive/folders/158ceibgYDFB6q0fiuF9sjJjQCulgtK2f?usp=sharing)

3. *Audio Dataset*  
   - Contains audio clips derived from the same 6 violent classes in the multi-class violent dataset and a non-violent class.
   - Includes environmental sounds, fight noises, explosion sounds, and more to improve robustness.
   - [Download Audio Dataset](https://drive.google.com/drive/folders/158ceibgYDFB6q0fiuF9sjJjQCulgtK2f?usp=sharing)

### Violence Categories  
Below is an image that visualizes different violent categories from the XD-Violence dataset:

![Violence Categories](https://github.com/Lathika-Wathsara/Movie-Violence-and-Non-Violence-Detection-and-Rating-System/blob/d3a877be73b2155f04f644a580305f732b21a1eb/Categories.jpg)

> Replace the link with the appropriate one to your dataset image or diagram.

---

## Installation

### Prerequisites
- Python 3.8 or later
- TensorFlow 2.7
- Keras
- MoviePy
- Scikit-learn
- OpenCV


