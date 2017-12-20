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
    - paper is very straightforward and is easy to understand.

### 2) Haar-Like Features
  - Foundation of Viola-Jones Algorithm which is actually used in open city. 
  - Hungarian mathematician in the 19th century, Alfred Haar, developed the mathematical concept called the haar wavelet, basis of wave function, fourier 
  - descendants of haar wavelet
  - what is it?
    - 1) Edge features
    - 2) Line features
    - 3) Four-rectangle features
  - pixel, identify end of table, columns of pixels, how they work out
  - e.g. haar-like features (mouth lips, line feature for instance)
  - e.g. edge features (eyebrow vs. lighter forehead)
  - e.g. edge features (nose, bridge of the nose - greyscale, line type of feature
  - pixel - greyscale (0 to 255) normalized to 0 and 1
  - real world, average intensity, average intensity, simply subtract one from the other
  - B - W = 0.402, closer to 1 the closer to real-world (depends on lighting, never going to be exact 1)
  - threshold are indentified through training
 
### 3) Integral Image 
  - Hack used in the Viola-Jones Algorithm, part of the success of the algorithm can be attributed to this integral image. 
  - Haar-like features (commonly found features on the face, calculated through the pixel value, threshold, calculate if feature is present or not, sum of all the values) -> quite a costly computation, lots of time and power
  - Hack to do the above quickly
  - Integral Image
    - 0 to 10, easier to look 
    - value for every single feature (calculate haar-like feature, intensity in the box, can be computationally expensive, real-time computer vision is costly for time, minimize time spent on this. Construction of integral image, exactly the same size
    - Any square in intergral, sum of the original image above and to the left, and fill the entire integral image that way (rectangle)
    - very efficient hack, it works because they're rectangles
    - you'll only need to look at four values regardless of the size of the rectangle (1000 x 1000) -> 4 vs. 1 million, image doesn't change propotionally, possible haar-like features are rectangles
    - might be a bit rigid, with computation efficiency
    
### 4) Training Classifiers
  - How the training process actually happens. 
  - Two stages (training & detection)
  - Training these feautres (five basic feature, narrow, long, which of them descriptive of a face common features of a face)
  - An algorithm won't know common features (beard, lighting etc.) help algorithm know which is important and not
  - Threshold, greayscale, 100% dark and clsoe to dark contast has to exceed the threshold. algorithm understand the threshold
  - Shrinks 24px 24px (why does it shrink)? -> features are scalable, 500x500 different variations (10x10, 100x100) etc. take forever to look through, scale down very limited, find still dark but you're actually applying it, scale the features up.
  - training scale down, in real life detecting, scale features up.
  - Missing is data, one image is not enough, we need to supply lots of images, which of the features is common, finding a face, 4916 manually label like each one instance a face, 24px, training your own algorithm, for all the face, take a mirror image, it's a brand new image, they instantly double the number images 9000 to 10000, features for faces. common just for faces
  - need to supply non-face images 9544 images don't have to be 24px, treat each one as a seperate (150,000 million etc.) 
  
### 5) Adaptive Boosting (Adaboost)
  - Another hack used to help the viola-jones algorithm in its success
  
### 6) Cascading
  - Another hack to really speed up the viola-jones algorithm, OpenCV
