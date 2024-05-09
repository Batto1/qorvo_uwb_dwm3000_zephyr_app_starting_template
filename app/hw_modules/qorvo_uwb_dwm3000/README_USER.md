## Brief
The original repository is a SDK port to Zephyr which includes numerous examples. Some unnecessary files are filtered out from that repo so that the other useful software such as driver code can be used conveniently for any application. Other than that, some files are useful but they're not included in the folder because they can not be targeted by build system when they reside in here. 

### Files That Are Filtered Out From the Original Repository
Additional information about the files & folders that are filtered out are given below:
- boards (folder): Zephyr doesn't allow files inside this folder to be  targeted in a custom file in CMakeLists.txt and it should be included before some other configurations. User might not be able to catch this or his foldering system might be different. Thus, to not add complexity into linking it's left out for user to use this folder as he wish.
- dts (folder): Zephyr allows files inside this folder to be  targeted in a custom file in CMakeLists.txt but it should be included before some other configurations. User might not be able to catch this or his foldering system might be different. Thus, to not add complexity into linking it's left out for user to use this folder as he wish.
- examples (folder): removed from the file because it isn't necessary for when developing custom applications.
- main.c: removed from the file because it isn't necessary for when developing custom applications.

### Additional Files Included in the Folder
- CMakeLists.txt: Added for making necessary CMake configurations.
- Kconfig: Added for making necessary Kconfig configurations.

## Usage
The folder that includes this file (qorvo_uwb_dwm3000) should be targeted by some upper-level parent folder's CMakeLists.txt and Kconfig. The rest of the configurations will be handled by this folder's targeted CMakeLists.txt and Kconfig files, for in them the necessary configurations are already presented.
Targeting can be made as shown below:

**In some upper-level parent folder's CMakeLists.txt, following line should be added in it:**

```
add_subdirectory(<other file directory in between>/qorvo_uwb_dwm3000)

```

**In some upper-level parent folder's Kconfig, following line should be added in it:**

```
menu "your_optional_menu_name"

rsource "<other file directory in between>/qorvo_uwb_dwm3000/Kconfig"
 
endmenu

```

## Original Repository Information
The [original repository][original_repository] is a SDK port to Zephyr which includes numerous examples for Qorvo UWB (Ultra-wide band) DWM3000 modules.

## Git Clone Information
Repository is cloned from the [commit b9b7db0 dated Nov 22, 2023][commit_b9b7db0] from the [original repository][original_repository].

[commit_b9b7db0]: https://github.com/foldedtoad/dwm3000/commit/b9b7db0289ea1af9e29243783264b05a8db7eb1c
[original_repository]: https://github.com/foldedtoad/dwm3000