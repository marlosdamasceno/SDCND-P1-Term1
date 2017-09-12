# **Finding Lane Lines on the Road** 

## Marlos Damasceno

---

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./test_images_output/image6.jpeg "Lines"

---

### Reflection

### 1. Brief description of my pipeline and draw_lines() function.

My pipeline (`process_image` function) consisted of 5 steps. 
1) I converted the images to grayscale.
![alt text][image1]
2) I blured the image using a Gaussian filter.
3) I got the edges using Canny.
4) I did a mask on the regions of interest, using vertices based on the image resolution.
5) I applied the Hough transformation and got the lines.
![alt text][image2]
6) I merged the lines with the orginal image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
