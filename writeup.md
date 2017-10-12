# **Finding Lane Lines on the Road** 
---

### 1. Pipeline Explanation

Step - 1 (Detect lanes from images) 

- Apply 5*5 gaussian filter for the input image.
- Perform canny edge detection on the blur image and get edge.
- Find regions of interest.
- Perform hough transform and get segment of lines.
- Append lines into original image. 

Step - 2 (Detect connected lines from videos) 

- Detect lanes for all images as used in step - 1.
- Connect Lines
  > Calculate constant 'b' from hough space.
  > Calculate average constant.
  > Get x and y from left and right lanes.
  > Connect lane points together.

### 2. Potential Shortcomings

- Algorithm not generalise well for all distributions.

### 3. Improvements

- Use grid search method to select the best Hough transform parameters.
