# computer-vision-face-detection

Overview
- 1) Viola-Jones Algorithm 
- 2) Haar-Like features 
- 3) Integral Image 
- 4) Training Classifiers
- 5) Adaptive Boosting (Adaboost)
- 6) Cascading

### 1) Viola-Jones Algorithm
  - Learn what it is, how it was created, and how it is still to this such a powerful algorithm despite it being created more than ten years ago.
  - Background:
    - Algorithm lies at the foundation of OpenCV
    - One of the most powerful algorithm for CV
    - Developed in 2001, over 16+ years and it's still one of the most powerful algorithms
    - Slowly surpassed by Deep Learning, real-time computer vision, extremely powerful
  - Two stages of the Viola-Jones Algorithm
    - 1. Training
    - 2. Detection
  - Start with Detection
    - Start with detection, how it works when it's trained already
    - Training will make much more sense. 
  - E.g. (Photo of a face)
    - Frontal face, viola-jones is designed for looking for frontal face
    - 1) turned into gray-scale (less data to process)
    - 2) starts looking for the face, little box left top corner down, 
    - 3) looking for certain features (e.g. eyebrows, eyes, forehead, cheeks etc.) 
    - 4) detects an eyebrow, might be a face...needs eye, nose, eyebrow etc. 
    - 5) if it can't detect, moves on to the right (same thing, loop) 
    - 6) nothing, nothing then it goes down
    - 7) might look for the nose next, no nose, it's not a face
    - 8) finally, it detects that there are two eyes, nose, mouth, cheeks, etc. -> depends on the training of the algorithm
    - 9) highlights the likelyhood it's a face. Facebox, boxes overlap, green square in any phase detection on your phone
   - Nutshell, how the box travel through the image. Now, talk about features and other hacks this process can expediated and faster.
   - Additional reading: Paul Viola & Michael Jones, 2001
Rapid Object Detection using a Boosted Cascade of Simple Features
   - http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.10.6807&rep=rep1&type=pdf

### 2) Haar-Like Features
  - Foundation of Viola-Jones Algorithm which is actually used in open city. 

### 3) Integral Image 
  - Hack used in the Viola-Jones Algorithm, part of the success of the algorithm can be attributed to this integral image. 

### 4) Training Classifiers
  - How the training process actually happens. 
  
### 5) Adaptive Boosting (Adaboost)
  - Another hack used to help the viola-jones algorithm in its success
  
### 6) Cascading
  - Another hack to really speed up the viola-jones algorithm, OpenCV
