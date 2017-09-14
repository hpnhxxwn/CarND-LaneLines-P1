### Most word done on this project is draw_line() function that combines all the lines identified into a left lane line and a right lane line.
1. Group all the lines into two categories according to the slope range and the intercept range. Lines out of range are filtered out. Left vertical is Y-axis, and top horizon is X-axis. The slop of left line should be some value between -0.5 to -0.9, and should intersect with horizontal bottom line. The slop of right line should be some value between 0.5 to 0.9, and should intersect with horizontal bottom line as well.  
2. Calculate average slop and intercept for left and right lines.
3. Draw lines using the calculated values.

In order to find more lines, the parameters for gaussian_blur(), canny(), and hough_lines() are not big because I want to capture more lines. Undesired lines are fitered out.

### Shortcomings and possible improvents
As can be seen in the challenge video, the algorithm cannot track well on the left side. The left line is somewhat shaky. One reason I can think of is that the algorithm does not treat the yellow color well. It can do well on some yellow color, but does not do well on other yellow color. More color tuning is needed. 

Only using line detection will fail for unideal situation, and most situations are not ideal. For example, the color of line caught by camera can be off due to weather difference, or color seen at the neight is different then in the morning. 
 
Moreover, the current algorithm will likely to fail if the camera's relative position to the car is changed, or there are lots of objects around cars that contributes to noises that make the algorithem falsely treat the lines of them as lane lines. The algorithm should be made independent on camera's relation position to car. We can use CNN to extract features (edges/lines).
