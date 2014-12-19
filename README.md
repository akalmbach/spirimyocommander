Once you have everything installed, you can use SpiriMyoCommander as follows:

Make sure you have an android device which supports bluetooth, with wifi turned on, and a charged Myo.

1) Start the app
2) Start a roscore, note the ROS_MASTER_URI
3) On the phone, where it says Robot URI, enter the ROS_MASTER_URI, then click connect.
4) In the top right there is a button which says "Scan". Click it, and from the next menu select the Myo
that you want to connect to. Then press back to get back to the main page.
5) Do the arm detection gesture with the Myo on.
6) On the screen, you'll see some debug information about the gesture the Myo is seeing and the cmd_vel
being published. You should be able to rostopic echo cmd_vel from the machine with the roscore and see
values being published.

The controls are implemented as follows (they can easily be changed, and probably should be)


Arm Pitch & Fist Gesture -> Front/Back Speed
Arm Yaw & Fist Gesture -> Yaw Speed
Fingers Spread Gesture -> Go up
Pinky to Thumb Gesture -> Go down
Anything Else -> Hover
