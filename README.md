VDB Mapping Core Library
===
DISCLAIMER: This library is still under development. Be warned that some interfaces will be changed and/or extended in the future.

This package is ROS2 port of [VDB Mapping](https://github.com/fzi-forschungszentrum-informatik/vdb_mapping)

The VDB Mapping core library was primarily developed to be used in combination with the corresponding [ROS wrapper (Under Development)](https://github.com/omerfkaya/vdb_mapping_ros)

## Getting Started

### Requirements
This library requires [OpenVDB](https://www.openvdb.org/) as it is build around it. This library was initially developed using Version 5.0 and should work with all versions above.  
 Either install the apt package:  
 Ubuntu 20.04
 ``` bash
 sudo apt install libopenvdb6.2
 ```
or compile the package from source using the provided [build instructions](https://github.com/AcademySoftwareFoundation/openvdb)

### Build instructions

The library can be either used as plain c++ library or in combination with the afore mentioned ROS wrapper.

#### Plain cmake
To build this package as a standalone library, follow the usual cmake building steps:
``` bash
git clone https://github.com/omerfkaya/vdb_mapping.git
cd vdb_mapping
mkdir build && cd build
cmake ..
make -j8
make install
```

#### ROS workspace
In case you want build this library inside of a ROS workspace in combination with [VDB Mapping ROS (Under Development)](https://github.com/omerfkaya/vdb_mapping_ros)

``` bash
# source global ros
source /opt/ros/<your_ros_version>/setup.bash

# create a catkin workspace
mkdir -p ~/colcon_ws/src && cd colcon_ws

# clone packages
git clone https://github.com/omerfkaya/vdb_mapping.git

# install dependencies
sudo apt update
rosdep update
rosdep install --from-paths src --ignore-src -y

# build the workspace.
colcon build --symlink-install

# source the workspace
source install/setup.bash

```