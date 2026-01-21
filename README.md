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
west init -l manifest-repo
west update
west zephyr-export

## Build for example app-blinky
cd app-blinky
west build -p always -b nucleo_f413zh
