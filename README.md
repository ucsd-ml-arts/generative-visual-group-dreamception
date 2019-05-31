# Project 4 Generative Visual

Matthew Rice, mhrice@ucsd.edu

## Abstract
-model is inception
Include your abstract here. This should be one paragraph clearly describing your concept, method, and results. This should tell us what architecture/approach you used. Also describe your creative goals, and whether you were successful in achieving them. Also could describe future directions.

## Model/Data
*tensorflow_inception_graph.pb* - Deepdream inception5h model \
[Inception Dream is Collapsing](https://www.youtube.com/watch?v=TRDbQwi3T8k) - Base video used to generate the output (used only 1:49 - end)

## Code
*MyDeepDream.ipynb* - Notebook used to instantiate the deep dream model and run the algorithm on images. Modified from [here](https://github.com/roberttwomey/ml-art-code/blob/master/week8/deepdream/deepdream.ipynb)\
*1_movie2frames.sh* - Converts a movie into frames at a rate of 30 frames per second. Adapted from [DeepDreamVideo](https://github.com/graphific/DeepDreamVideo)

## Results
*dreamception.mp4* - Output video with all of the frames  [Link]\
*deepdreamtest.mp4* - Short test output using random frames [Link]\
*frames/* - Directory with all the processed frames [Link]\

## Technical Notes
First run `./1_movie2frames.sh ffmpeg [original_video] [frames_directory] jpg` to split the video into frames. Then run through the steps of the notebook to reproduce the output. I used every other photo for the deepdream algorithm (thus converting 30fps to 15fps) to save on time. This process took around 24 hours to complete for a 90 second video, processing about 1 frame per minute. 
*Note ffmpeg is needed to generate the video from the frames.

## Reference
[DeepDream](https://ai.googleblog.com/2015/06/inceptionism-going-deeper-into-neural.html)\
[DeepDreamVideo](https://github.com/graphific/DeepDreamVideo)
