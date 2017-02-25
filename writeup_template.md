#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I use gaussian filter to reduce noise. 
After this i uses canny edge to detect the lines and then mask the region that i needed with region_of_interest function already defined.
Finally with the help of hough transform we  get the deisred lane lines and then mark these lane lines onto the original image.

In order to draw a single line on the left and right lanes, I have made another function extrapolate. In that lines_linreg function will give you y,x,m ,c for all the lines.
then for the positive slope lines we will get the average of slope(m) and intercept(c). Same for negative slope lines. Then after that we redraw the single line with the help of average slope (m) and c. 




###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the road are more curved not straight.

Another shortcoming could be when lane lines are not marked , when you are driving in hilly areas or where the slope of road changes then our area of interest 
goes wrong.


###3. Suggest possible improvements to your pipeline

A possible improvement would be not to redraw straight lines by taking mean of slope. We have to define slope at all the infinitesimal points and than redraw the curve out of it. not just taking mean.

Another potential improvement could be  with the help of road color we can define the region of interest.