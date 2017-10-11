# **Finding Lane Lines on the Road** 

---

### 1. Pipeline Explanation

Step - 1 (Detect lanes from images) 

- Apply 5*5 gaussian filter for the input image.
- Perform canny edge detection on the blur image and get edge.
- Find regions of interest from the edge.
- Perform hough transform and get line segments.
- Append lines into original image. 

Step - 2 (Detect connected lines from videos) 

- Detect lanes for all images as used in step - 1.
- Connect Lines
  > Get slope of the lines.
  > Calculate positive and negative slopes.
  > Calculate average slopes.
  > Calculate constant 'b' from hough space.
  > Calculate average constant 'b'.
  > Get x and y from left and right lanes.
  > Connect points together as lane.

### 2. Potential Shortcomings

- There are a few instances in the yellow lane line video where the lane lines are marked incorrectly. The error is always (to my knowledge) in the lane line that is not solid.
- Image dimensions were hard-coded in at least one case.
- If the lane lines are not straight lines but have high curvature, this algorithm may give weird results.
- The algorithm was trained on a specific type of lane and type of day (daytime, moderately bright with no snow, rain or hail), so it may not generalise well.

### 3. Improvements

- Tune Hough transform parameters more systematically with more test images instead of by 'feel'.
- Currently the lane lines are drawn in solid white. It would be nice if they were drawn in thicker, semi-transparent red.
