# **Finding Lane Lines on the Road** 

## Marlos Damasceno

[//]: # (Image References)

[image1]: ./test_images_output/gray.jpeg "Lines"
[image2]: ./test_images_output/blur.jpeg "Lines"
[image3]: ./test_images_output/canny.jpeg "Lines"
[image4]: ./test_images_output/masked.jpeg "Lines"
[image5]: ./test_images_output/hough.jpeg "Lines"
[image6]: ./test_images_output/image6.jpeg "Lines"

---

### Reflection

### 1. Brief description of my pipeline and draw_lines() function.

My pipeline (`process_image` function) consisted of 6 steps. 
1) I converted the images to gray scale.
![alt text][image1]
2) I blurred the image using a Gaussian filter.
![alt text][image2]
3) I got the edges using Canny.
![alt text][image3]
4) I did a mask on the regions of interest, using vertices based on the image resolution.
![alt text][image4]
5) I applied the Hough transformation, extrapolation and got the lines.
![alt text][image5]
6) I merged the lines with the original image
![alt text][image6]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by checking for the signal of the slope, negative on the left and positive on the right. Moreover, I add a range for the slopes from 0.5 to 0.8 to have a good inclination of the line. After that, I did the average of the m's and b's of the lines of which side resulting in two "averages" lines that I extrapolate using the line equation. Plus, the left line is green and the right is red.


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when there is a high contrast part of the image inside the region of interest that is similar to the lines, like another paint on the road or asphalt differences (as in the challenge video). Moreover, could be the opposite, where there such low contrast between the line and the asphalt that the line can not identified.
Another shortcoming could be a hard curve, because would change a lot the slope.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be filter the lines by the pixels colors before change it to gray scale. That would allow to get the white and yellow pixies of the lines resulting in much better detection of the lines.
Another potential improvement could be to a time decency between the frames of the video, that would result in smooth changes of lines during the video.
