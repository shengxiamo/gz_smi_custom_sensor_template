# Custom sensor plugin in Gazebo Fortress

## Modification
### implement custom sensor class
The custom sensor class should inherit from ignition::sensors::Sensor and implement both Load() and Update() functions. In this template, it is named Odometer, which you can rename as needed. You should also create a public interface that will be used by the system class.

### implement custom system  class
The custom system class is required to implement two virtual functions: PreUpdate() and PostUpdate(). Your custom sensor class's interface should be appropriately used within these two functions.
### edit the .sdf file
TBD.
## Build
From the root of the this project, do the following to build:
```bash
mkdir build
cd build
cmake ../custom_sensor_system/
make -j
```

## Run
The plugin must be attached to an entity to be loaded. This is demonstrated in the odometer.sdf file that's going to be loaded.

Before starting Gazebo, we must make sure it can find the plugin by doing:
```bash
export IGN_GAZEBO_SYSTEM_PLUGIN_PATH=`pwd`/build
```
Then load the example world:
```bash
ign gazebo -r odometer.sdf
```

## Refernces
All code samples were derived from Open Source Robotics Foundation's repositories:

https://github.com/gazebosim/gz-sensors/tree/ign-sensors6/examples/custom_sensor

https://github.com/gazebosim/gz-sim/tree/ign-gazebo6/examples/plugin/custom_sensor_system