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

### 1.  Pipeline Describition. 

My pipeline consisted of 6 steps. 

 - First, I converted the images to grayscale by using **cv2.cvtColor** method.
 - Second, I applied a Gaussian blur to the provided image using **cv2.GaussianBlur** method.
 - Third, I Used a Canny transformation to find edges on the image by using **cv2.Canny** method.
 - Fourth: I Eliminated parts of the image that are not interesting in regards to the line detection.
 - Fifty: I used a Hough transformation to find the lines on the masked image by using **cv2.cv2.HoughLinesP**. 
 - Finally: I merged the output of houghAction with the original image to represent the lines on it.
 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function:

 - First, I seperated the line to the left part and right part by cal the slope
 - Second, I removed the lane which is not closed the other lines in the part.
 - Third, I use the method **np.polyfit** to find the finally line.



### 2. Identify potential shortcomings


One potential shortcoming would be what would happen when the road is not straight.

Another shortcoming could be when the camera changed either the device changed or the device's position changed 


### 3. Suggest possible improvements

As described，A possible improvement would be to find a better transform to detect curved lanes.

Another potential improvement could be to make the function more robust to adapt diffierent device.

