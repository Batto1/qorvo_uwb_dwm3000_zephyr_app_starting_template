# SPDX-License-Identifier: Apache-2.0
cmake_minimum_required(VERSION 3.20.0)


## !!!
## WARNING: After setting new configurations, delete the build file and create a build configuration again to make sure they are applied since some configurations already existing in the CMake cache are prioritized when building.
## !!!


############ .conf files settings START ############
# add_subdirectory(conf) # it's found out that this for some reason doesn't work correctly when you make nested CMakeLists.txt files like how it works with 'app' folder and then set the configuration files. Thus a CMakeLists.txt file you'll put in 'conf' file doesn't actually include the configurations so instead they're set here.

# Below configuration setting has to be made before "find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})" line.
# set one setting first. It's the prj.conf because otherwise it's omitted. 
set(CONF_FILE "prj.conf")
# and then follow the syntax given below
set(CONF_FILE "${CONF_FILE};conf/common/qorvo-uwb-dwm3000.conf")
# set(CONF_FILE "${CONF_FILE};conf/common/qorvo-uwb-dwm3000-debug-and-log.conf")
############  .conf files settings END  ############



############ set board START ############
# If you only want to build for one board, add the name of the board configuration for your application on a new line.
set(DTS_ROOT   "${CMAKE_CURRENT_SOURCE_DIR}")
set(BOARD_ROOT "${CMAKE_CURRENT_SOURCE_DIR}")
set(SHIELD qorvo_dwm3000)

set(BOARD nrf52840dk_nrf52840)
############  set board END  ############



############ set overlay files START ############
# consequtive sets with arguments DTC_OVERLAY_FILE or EXTRA_DTC_OVERLAY_FILE override each other, you need to seperate the file directories with semicolons. Syntax given below can be used to seperate them over multiple lines.
# set(DTC_OVERLAY_FILE "boards/overlays/nrf52840dk_nrf52840.overlay")
# set(DTC_OVERLAY_FILE "${DTC_OVERLAY_FILE};boards/overlays/custom_overlay_1.overlay")

# EXTRA_DTC_OVERLAY_FILE: This can be useful to leave DTC_OVERLAY_FILE at its default value, but “mix in” some additional overlay files. (Zephyr Documentation: Application Development)
# set(EXTRA_DTC_OVERLAY_FILE "boards/overlays/custom_overlay_2.overlay")
# set(EXTRA_DTC_OVERLAY_FILE "${EXTRA_DTC_OVERLAY_FILE};boards/overlays/custom_overlay_3.overlay")
############  set overlay files END  ############



find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(structured_zephyr_app_template)



############ setting source and header files START ############
# adding subdirectory to reach other CMakeLists.txt files in other nested files.
add_subdirectory(app)

# below is the line for conditinally adding a subdirectory depending on a configuration
# add_subdirectory_ifdef(CONFIG_CUSTOM_CONFIG_EXAMPLE app)


# main.c will be targeted in app > core directory thus below line is commented out.
# target_sources(app PRIVATE src/main.c)
############  setting source and header files END  ############


