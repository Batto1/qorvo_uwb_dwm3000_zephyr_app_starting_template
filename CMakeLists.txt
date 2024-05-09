# SPDX-License-Identifier: Apache-2.0


cmake_minimum_required(VERSION 3.20.0)

## !!!
## WARNING: After setting new configuration files, delete the build file and create a build configuration again 
## !!!


# Below configuration setting has to be made before "find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})" line.
# set one setting first. It's the prj.conf because otherwise it's omitted. 
set(CONF_FILE "prj.conf")
# and then follow the syntax given below
# set(CONF_FILE "${CONF_FILE};conf/common/example-conf1.conf")



find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(qorvo_uwb_dwm3000_app_starting_template)

# adding subdirectory to reach other CMakeLists.txt files in other nested files.
add_subdirectory(app)

# below is the line for conditinally adding a subdirectory depending on a configuration
# add_subdirectory_ifdef(CONFIG_CUSTOM_CONFIG_EXAMPLE app)


# main.c will be targeted in app > core directory thus below line is commented out.
# target_sources(app PRIVATE src/main.c)



