# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following:
1. The image is converted into gray scale
2. The gray scale image is filtered with a gaussian filter to remove noise and prepare it for edge detection
3. Canny edge detection is applied
4. A quadrilateral is defined by its vertices and used to only keep the region of interest in the image of edges
5. Hough lines algorithm is applied to find lines in edges
6. The lines found are combined with the original image to show them together
7. The lines found by hough algorithm are passed to an averaging algorithm that calculates two average lines representing the right and the left lanes.
The algorithm first divides lines into right and left lines depending on the slope
It then finds an average slope for each group weighted by the length of the line
8. The two average lines are drawn on the original image to represent the lanes



### 2. Identify potential shortcomings with your current pipeline


A short coming of this algorithm is that the lane lines are wiggling a lot in the video


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to average the identified lines form frame to frame
