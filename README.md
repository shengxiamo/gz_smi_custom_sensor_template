# Custom sensor and use in Gazebo Fortress

## Modification
### implement custom sensor class
custom sensor class should inherits and required to implement Load() and  Update() functions. In this template, it named Odometer and you can rename it.You should also create public interface to be used in system class.

### implement custom system  class

### edit the .sdf file

## Build
From the root of the this project, do the following to build:
```bash
cd custom_sensor_system
mkdir build
cd build
cmake ..
make -j
```

## Run
The plugin must be attached to an entity to be loaded. This is demonstrated in the odometer.sdf file that's going to be loaded.

Before starting Gazebo, we must make sure it can find the plugin by doing:
```bash
cd custom_sensor_system/
export IGN_GAZEBO_SYSTEM_PLUGIN_PATH=`pwd`/build
```
Then load the example world:
```bash
ign gazebo -r odometer.sdf
```

## Refernces
all these were copied from Open Source Robotics Foundation's code repositories:
https://github.com/gazebosim/gz-sensors/tree/ign-sensors6/examples/custom_sensor
https://github.com/gazebosim/gz-sim/tree/ign-gazebo6/examples/plugin/custom_sensor_system