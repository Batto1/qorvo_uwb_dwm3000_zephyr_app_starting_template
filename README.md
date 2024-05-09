## Overview
This file contains necessary DWM3000 library links and configurations to start developing applications with DWM3000 module easily on [Zephyr Platform][Zephyr_Platform].

[Zephyr_Platform]: https://docs.zephyrproject.org/latest/introduction/index.html

## Usage

The file tree structure is based on a modified version of [this template][file_tree_structure_template].

[file_tree_structure_template]: https://github.com/Batto1/Structured-Zephyr-App-Template

It's easy to work with and namings are mostly self explanatory. The application files you'll be developing over this template should optionally reside in 'app' folder. You can use the existing file structure in this folder to separate and categorize files or you can implement your own file tree structure strategy by making some small modifications. 

## Qorvo UWB DWM3000 Files Transferred Over From the Original Repository
The [original repository][original_repository] is a SDK port to Zephyr which includes numerous examples for Qorvo UWB (Ultra-wide band) DWM3000 modules. 
Repository is cloned from the [commit b9b7db0 dated Nov 22, 2023][commit_b9b7db0] from the [original repository][original_repository].

[commit_b9b7db0]: https://github.com/foldedtoad/dwm3000/commit/b9b7db0289ea1af9e29243783264b05a8db7eb1c
[original_repository]: https://github.com/foldedtoad/dwm3000

- boards (folder): Original repository has board options for choosing the DWS3000 shield. This file is provided in the /boards directory of this template.
- dts (folder): Original repository has dts binding options for the DWS3000 shield. This file is provided in the /boards directory of this template.
- app > hw_modules > qorvo_uwb_dwm3000 (folder): The rest of the necessary files are given in this folder. This folder contains other source and header files such as drivers for utilizing DWM3000.
- the rest of the files from the original repository are example files and 'main.c' file which only ensures compability along the examples and for while creating Zephyr applications. These files are omitted in this template but they can be used as a reference when developing your own applications.

## Building and Running
- You can follow the [original repository][original_repository]'s instructions for building and running.
- You can use nRF Connect SDK of Nordic Semiconductor if you're using Nordic products. 


### CMake Configurations For Setting DWS3000 Shield
To set the DWS3000 shield, before the 

```
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
```
line, following lines should be included in the CMakeLists.txt file at the beginning of it for setting the board and dts binding files. If the directory of those files are changed, these CMake lines should be modified accordingly, too.

```
set(DTS_ROOT   "${CMAKE_CURRENT_SOURCE_DIR}")
set(BOARD_ROOT "${CMAKE_CURRENT_SOURCE_DIR}")
set(SHIELD qorvo_dwm3000)
```