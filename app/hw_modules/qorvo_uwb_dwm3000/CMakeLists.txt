# SPDX-License-Identifier: Apache-2.0




# add_subdirectory()



if(CONFIG_QORVO_UWB_DWM3000)
     target_sources(app PRIVATE config_options.c)

     target_sources(app PRIVATE decadriver/deca_device.c)

     target_sources(app PRIVATE MAC_802_15_4/mac_802_15_4.c)
     target_sources(app PRIVATE MAC_802_15_8/mac_802_15_8.c)

     target_sources(app PRIVATE platform/deca_sleep.c)
     target_sources(app PRIVATE platform/deca_spi.c)
     target_sources(app PRIVATE platform/port.c)
     
     target_sources(app PRIVATE shared_data/shared_functions.c)

     target_include_directories(app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/)
     target_include_directories(app PRIVATE compiler/)
     target_include_directories(app PRIVATE decadriver/)
     target_include_directories(app PRIVATE MAC_802_15_4/)
     target_include_directories(app PRIVATE MAC_802_15_8/)
     target_include_directories(app PRIVATE platform/)
     target_include_directories(app PRIVATE shared_data/)

     # line below makes possible to include the header files as << #include "example_module.h" >> in source files without specifying the folder location such as << #include "example_module/example_module.h" >>
     # With this specific configuration, user will be able to include directories as <#include "qorvo_uwb_dwm3000/example_folder/example_file.h"> or <#include "example_folder/example_file.h"> or <#include "example_file.h">
     zephyr_include_directories(../)
     zephyr_include_directories(${CMAKE_CURRENT_SOURCE_DIR}/)
endif()

