# myZephyrWorkspace

Zephyr RTOS workspace using **forest topology** with a **freestanding manifest repository**.

## Zephyr version
- Zephyr: 3.7 LTS
- SDK: 0.16.8

## Board Tested For
- STM32F413ZH
- Nucleo-F413ZH

## Setup for Windows users
### Run the following command from inside myZephyrWorkspace
```cmd
mkdir D:\Study\myZephyrWorkspace
cd D:\Study\myZephyrWorkspace

west init -m https://github.com/YashGiramkar/myZephyrWorkspace.git
west update
```


## Build for example app-blinky
```cmd
west build -b nucleo_f413zh app-blinky
```
