# Cat and Mouse Game V2
In the second approach, the two main problems that were seen in the first implementation, proximity control and search for the drone-mouse in case of loss, will be solved.

## Proximity Control
Closeness control
To control how close the drone-mouse is, the area of ​​the detected contour will be used.

The difference with the current area is calculated from an initial area and is used for the P controller of the variables vx or vz, depending on which camera the drone-mouse was detected with.

With this solution we have results like the following video

[![](https://img.youtube.com/vi/bE7tJDUa7ko/0.jpg)](https://youtu.be/bE7tJDUa7ko)

## Drone-mouse search
In case the drone-cat loses sight of the drone-mouse, or does not find it from the first moment, the search will start.

If the drone-mouse was present in the previous frame, it will follow the direction in which it was. On the contrary, if it was not from the first moment or it takes several frames without appearing in one of the two cameras, the drone-cat will begin to rotate on itself and rise until the drone-mouse enters its field of vision.

[![](https://img.youtube.com/vi/-yU7YdoOib8/0.jpg)](https://youtu.be/-yU7YdoOib8)