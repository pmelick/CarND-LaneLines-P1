#**Finding Lane Lines on the Road** 

##pmelick 2/26/16
[//]: # (Image References)

[gray]: ./report_images/gray_image.jpg "Gray"
[blur]: ./report_images/blur_image.jpg "Blur"
[canny]: ./report_images/canny_image.jpg "Canny"
[roi_only]: ./report_images/roi_only_image.jpg "ROI"
[hough]: ./report_images/hough_image.jpg "Hough"
[lines]: ./report_images/lines.jpg "Lines"

### Reflection

My pipeline consists of six steps:

1. Convert image to grayscale.
![alt text][gray]
2. Blur image with a gaussian kernel.
![alt_text][blur]
3. Use Canny Edge Detection to find edges.
![alt_text][canny]
4. Remove any edges outside of a region of interest.
![alt_text][roi_only]
5. Use a hough transform to detect lines.
![alt_text][hough]
6. Fit two lines, left and right, to the lines detected by the hough transform.
![alt_text][lines]

###2. Identify potential shortcomings with your current pipeline

As I learned when I attempted my pipeline on the challenge data set, some potential problems include:
- Guard rails near the lanes, which also have long straight lines.
- The car's body partially occluding the field of view.

###3. Suggest possible improvements to your pipeline

Some possible improvements could be:
- Take the color of the lines into account, which I ignore right now.
- Use RANSAC to reject outliers before doing the best fit in the final step.
