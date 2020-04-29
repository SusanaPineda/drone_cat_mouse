# Cat and Mouse Game V1
As with F1 follows lines, the first approach we are going to make is a P controller for each of the control variables (vx, vy, vz).

In this case, to obtain the necessary information for the controller, we will first apply a color filter to locate the drone-mouse.

Once we have the filtered image we apply a series of erosions and dilations to eliminate the possible noise present in the image and we detect the contours using the OpenCV findContours function.

From the detection of contours, we stay with the one with the largest area and obtain its position. Using the position of the contour with the largest area, the error with respect to the center will be calculated and will be used for the controllers P of the variables vx, vy and vz that control the linear velocity in x, y and z.

If the drone-mouse is in front of our drone, that is, it is seen with the front camera, we can calculate the variables vy and vz, but at the moment we will not be able to calculate vx since it depends on how closely it is.

If the drone-mouse is below our drone, that is, it is seen with the vertical camera, the variables vx and vy will be calculated, but for the moment it will not be possible to calculate vz.

With this implementation we obtain results like those that can be seen in the following video.

With this implementation we have two main problems, we do not control how closely we are to the drone-mouse and that if we lose sight of the mouse we cannot locate it again.

[![](https://img.youtube.com/vi/deRKA741Qgk/0.jpg)](https://www.youtube.com/watch?v=deRKA741Qgk)