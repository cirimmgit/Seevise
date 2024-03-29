# Seevise
Simple AI-Driven System To Point Out Key Environment Objects


# Introduction (Backstory)
Over the past semester of high school, I was tasked with designing and creating a "senior project" based around community help and self-improvement. Currently, I am fascinated with the power of AI and the plethora of uses it may have, so I knew that I wanted to create something along these lines. A while back, my friends and I formed a team known as the "Ramen Club", where we would try to build something to help the blind in any fashion. While pitching ideas around, I introduced the idea of using computer vision software to alert the blind to environmental obstacles or objects of interest. After much discussion, we eventually scrapped that idea and moved on due to the lack of experience we all had in the field of computer vision. I never forgot that idea, however, and decided to throw caution to the wind and teach myself all that I could. After many weeks and a significant amount of challenges to overcome, I created the Seevise system (CV + eyes = Seevise). This project isn't the most optimized, and takes a significant amount of resources to run (eliminating the portability aspect of it), but the goal was simply to introduce the idea of using computer vision in this fashion. I also just wanted to overcome my 

# Introduction (How I made it)
This project is based around the phenomenal "Image Detection with YOLO-v2" youtube series by Mark Jay (linked below). I followed his advice for a significant chunk of this project, as I was entering this challenge with no prior experience. After following his his instructions on how to make a simple object detection program, I branched out to morph what I now had into my current vision. 

# Introduction (What It Does)
This project takes in realtime video via a webcam or camera and detects objects that may be helpful for the blind to know about in order to navigate a city/suburban environment. I initially focused on a few things, such as trash cans, crosswalks, cars, and more, but ended up with just the crosswalks/cars due to many errors involving large scale data collection for training. Once a traffic light or stop sign is detected in the camera, the code will automatically start a counter for how many frames in a row that object has been detected in order to eliminate "noise". After that, an audio cue alerts the user to the location and distance to the object. A timer prevents a constant stream of audio cues, and I currently have it set to 10 seconds for crosswalks. As for cars, I have it set to alert every 3 seconds, and only if the car is directly in front of the user. 

# Demonstration
[Gfycat Demonstration, Sound On](https://gfycat.com/unconsciouslavishamphiuma)

#Setup
1. Download the contents of this directory.
2. Go to https://drive.google.com/open?id=151z-AeCH4Gf4cBwdnwanRq6qP7ZeDgAH to download the bin directory.
3. Place the bin directory in the darkflow-master directory

# Usage
To run this code, navigate to the darkflow-master directory and run 
```
realtime.py
```
# Training
To train the code, create folders of training data sorted by object, and run 
```
python genx.py arg1 arg2 arg3 arg4
```
arg1 = object name (car)

arg2 = source folder (data/cars)

arg3 = annotations folder (train/annotations) This annotations folder contains all of the annotations, regardless of object

arg4 = images folder (train/images) This images folder contains all of the images, regardless of object

Once the training set is ready, you can follow the training instructions on the official Darkflow github repo, located at https://github.com/thtrieu/darkflow

# Dependencies
- Numpy
- OpenCV 3 
- Tensorflow 1.0
- Python 3

# Sources
Mark Jay: https://www.youtube.com/playlist?list=PLX-LrBk6h3wSGvuTnxB2Kj358XfctL4BM

Darkflow Github Repo: https://github.com/thtrieu/darkflow
