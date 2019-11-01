# sam_stonefish_sim

Prototype for simulating the SAM auv in stonefish. This is a work in progress
and support for the full SAM vehicle is not there yet. Right now we support
the following commands:
* `/sam/core/lcg_cmd` - `sam_msgs/PercentStamped` sets position of LCG weight 0-100%
* `/sam/core/rpm_cmd` - `sam_msgs/ThrusterRPMs` sets rpm of the two thrusters, forward is positive
* `/sam/core/thrust_vector_cmd` - `sam_msgs/ThrusterAngles` sets vertical and horizontal angle of thrusters

## Building

Let us start by installing the dependencies.
```
sudo apt install libsdl2-dev
```
If you are on Ubuntu 16.04, you need to use vim (or other editor) to open the file
```
sudo vim /usr/lib/x86_64-linux-gnu/cmake/SDL2/sdl2-config.cmake
```
and then remove space after "-lSDL2 ". On 18.04 this is not needed.

Now go into the catkin workspace where you want to build the simulation,
or create a new workspace. In the `src` folder, execute the commands,
```
git clone https://github.com/smarc-project/imc_ros_bridge.git
git clone https://gitr.sys.kth.se/smarc-project/sam_common.git
git clone https://bitbucket.org/iquarobotics/cola2_msgs.git
git clone https://github.com/nilsbore/sam_stonefish_sim.git
git clone https://github.com/nilsbore/stonefish_ros.git
cd stonefish_ros
git submodule update --init
```
**NOTE**: you need access to KTH gitr for the second package.
This and `imc_ros_bridge` are needed if you want to run the full stack but not if you just
want to start up the simulation with the robot.
