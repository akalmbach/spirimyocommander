##Installing
1. Install android-studio, the android sdk, and the myo sdk
2. Set up a ros android core workspace by running
```mkdir ~/android``` and then ```wstool init -j4 ~/android/src https://raw.github.com/rosjava/rosjava/hydro/android_core.rosinstall```
3. Clone this repo into ~/android/src/android_core
4. Edit ~/android/src/android_core/settings.gradle to include spirimyocommander
5. Import the android_core project into android-studio. It will try to configure and build the project
so this might take a little while.
6. Deploy as you would any other app

** Note, this is not really a good installation process. This project needs to be separated out
from the ros android_core package

##Running
Once you have everything installed, you can use SpiriMyoCommander as follows:

Make sure you have an android device which supports bluetooth, with wifi turned on, and a charged Myo.

1. Start the app
2. Start a roscore, note the ROS_MASTER_URI
3. On the phone, where it says Robot URI, enter the ROS_MASTER_URI, then click connect.
4. In the top right there is a button which says "Scan". Click it, and from the next menu select the Myo
that you want to connect to. Then press back to get back to the main page.
5. Do the arm detection gesture with the Myo on.
6. On the screen, you'll see some debug information about the gesture the Myo is seeing and the cmd_vel
being published. You should be able to rostopic echo cmd_vel from the machine with the roscore and see
values being published. There will also be a std_msgs/String gesture topic, with the name of the gesture being read.

The controls are implemented as follows (they can easily be changed, and probably should be)


Arm Pitch & Fist Gesture -> Front/Back Speed
Arm Yaw & Fist Gesture -> Yaw Speed
Fingers Spread Gesture -> Go up
Pinky to Thumb Gesture -> Go down
Anything Else -> Hover
