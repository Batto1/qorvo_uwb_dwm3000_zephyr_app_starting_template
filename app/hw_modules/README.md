## Brief
"HW Module" is defined as some individual hardware (HW) that mainly has some independent function than other HW modules in the system. HW modules generally has some specific interfacing options to work with other HW modules and are generally an IC or a PCBA (printed circuit board assembly) by itself. Can be externally connected to an individual programmable integrated circuit (IC) (such as MCUs, SoCs, SiPs etc.) or it can be the programmable IC itself which the application is built for. In this sense, for example, HW Modules in this folder's context are **not** defined as peripherals or any other physical module inside some individual IC (such as analog to digital converters (ADC), timers or some other module part of a MCU, SoC or SiP). These kind of modules reside under its own IC HW Module.

## Portability of Code
Code is portable since drivers for the HW are same. The interface between communicating HW may change depending on the application but this is not in this file's scope.

## Parent Folder Name
hw_modules

## Properties Of The Parent Folder 
The parent folder should contain this README file, some software (SW) files related with HW Modules (such as driver software), and any other necessary and related files. Files should be appropriately categorized and foldered as required.
