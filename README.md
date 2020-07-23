[//]: # (Image References)
[image1]: ./test_images_output/origin.jpg "origin"
[image2]: ./test_images_output/gray.jpg "gray"
[image3]: ./test_images_output/blur.jpg "blur"
[image4]: ./test_images_output/edges.jpg "edges"
[image5]: ./test_images_output/roi.jpg "roi"
[image6]: ./test_images_output/lines.jpg "lines"
[image7]: ./test_images_output/result.jpg "result"


Overview
---
Creating a project for Lanes detecting through camera from images and videos. Creating a whole pipeline for detection of the lanes


The project
---
The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Improve this pipeline



Ideas for Lane Detection Pipeline
---
Some OpenCV functions I have used for this project are:

cv2.line() to draw lines on an image given endpoints  
cv2.inRange() for color selection  
cv2.bitwise_and() to apply a mask to an image  
cv2.fillPoly() for regions selection  
cv2.addWeighted() to coadd / overlay two images cv2.cvtColor() to grayscale or change color cv2.imwrite() to output images to file  


Build a Lane Finding Pipeline
---
My pipeline consisted of 6 steps. 
![alt text][image1]

1. Convert the images to grayscale from RGB model 
![alt text][image2]  

2. Use cv2.GaussianBlur() to blur the image
![alt text][image3]  

3. Detecting edges of a gray model image
![alt text][image4]  

4. Defining a region of interest
![alt text][image5]  

5. Hough transform edges to a set of lines
![alt text][image6]  

6. Adding the lanes over original image
![alt text][image7]  


Test on videos
---
You know what's cooler than drawing lanes over images? Drawing lanes over video!

We can test our solution on two provided videos:

`solidWhiteRight.mp4`

`solidYellowLeft.mp4`  


Reflection
---
### 1. Identify potential shortcomings with your current pipeline


Biggest shortcoming of this project is that the reflective properties of the road and paint of the lanes can cause hotspots and can cause problems like varied outputs and even wrong outputs. 
Another shortcoming is that the program takes too long to process and give the output, and can cause delays and accidents. This might not be the best solution for the detection.


### 2. Suggest possible improvements to your pipeline

An improvement would be to use better technology and machine learning with real time satelites that could incorporate a better feed and better lanes detection overall and be faster and more accurate.

Attribution
---
https://github.com/udacity/CarND-LaneLines-P1/
https://buildmedia.readthedocs.org/media/pdf/opencv-python-tutroals/latest/opencv-python-tutroals.pdf
