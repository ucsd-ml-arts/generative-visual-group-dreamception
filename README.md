# Project 4 Generative Visual

Matthew Rice, mhrice@ucsd.edu

## Abstract
Since the beginning of this quarter, I was really facinated by the Google DeepDream project in creating psychedelic "dreams" of images and videos. I was interested in creating my own version of one of these videos. I decided to use the "Collapsing Dream" scene at the end of the film *Inception*. I chose this particular film since it encapsulated the idea of dreams as reality. I also chose this particular scene, since the idea of the dream collapsing mixed with the deep dream styled frames turns this experience into a nightmare. I also was inspired by the name of the model used for this project, "inception5h". 
To implement this, I used a script from the DeepDreamVideo repository(linked below) to split the 90 second edited scene into 2664 frames (30 fps). Although the DeepDreamVideo repository had a script to automate transforming each image into a DeepDream version and gluing them backtogether, unfortunatly, the script was written in Python 2.7 and required caffe which was not installed on our image. So I decided to implement the method myself using ideas from the DeepDream notebook that we tried in class. To save on processing time, I only processed every other image, and glued back the images at 15fps which did decrease the quality of the video. The processing took a full 24 hours (including a few restarts of the server), but ended up being successful. I think the final product amplies the intensity of the original dream collapsing scene in a freakish way. 

## Model/Data
[Inception5h Deep Dream Model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) - Model used for Deep Dream Image Generation \
[Inception Dream is Collapsing](https://www.youtube.com/watch?v=TRDbQwi3T8k) - Base video used to generate the output (used only 1:49 - end)

## Code
*MyDeepDream.ipynb* - Notebook used to instantiate the deep dream model and run the algorithm on images. Modified from [here](https://github.com/roberttwomey/ml-art-code/blob/master/week8/deepdream/deepdream.ipynb)\
*1_movie2frames.sh* - Converts a movie into frames at a rate of 30 frames per second. Adapted from [DeepDreamVideo](https://github.com/graphific/DeepDreamVideo)

## Results
*dreamception.mp4* - Output video with all of the frames  [Link](https://youtu.be/DTX_ZW3Mj9U)\
*deepdreamtest.mp4* - Short raw test output using random frames [Link](https://youtu.be/Q8WGfOdszwE)

## Technical Notes
First run `./1_movie2frames.sh ffmpeg [original_video] [frames_directory] jpg` to split the video into frames. Then run through the steps of the notebook to reproduce the output. I used every other photo for the deepdream algorithm (thus converting 30fps to 15fps) to save on time. This process took around 24 hours to complete for a 90 second video, processing about 1 frame per minute. After the video was complete, I added back the original audio, and uploaded it to YouTube.
*Note:* ffmpeg is needed to generate the video from the frames.

## Reference
[DeepDream](https://ai.googleblog.com/2015/06/inceptionism-going-deeper-into-neural.html)\
[DeepDreamVideo](https://github.com/graphific/DeepDreamVideo)
