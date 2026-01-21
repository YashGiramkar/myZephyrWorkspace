# myZephyrWorkspace

Zephyr RTOS workspace using **forest topology** with a **freestanding manifest repository**.

## Zephyr version
- Zephyr: 3.7 LTS
- SDK: 0.16.8

## Board Tested For
- STM32F413ZH
- Nucleo-F413ZH

## Setup for Windows users
First create a myZephyrWorkspace directory
```cmd
mkdir myZephyrWorkspace
```

Next clone this repository to manifest-repo folder inside myZephyrWorkspace.
You can run the following command on cmd from inside myZephyrWorkspace
```cmd
git clone https://github.com/YashGiramkar/myZephyrWorkspace.git manifest-repo
```



### Run the following command from inside myZephyrWorkspace
```cmd
west init -l manifest-repo
west update
west zephyr-export
```


## Build for example app-blinky
Change the directory to the required application directory:
```cmd
cd app-blinky
```
Perform selected application build
```cmd
west build -p always -b nucleo_f413zh
```

Or from the root repository you can just do :
```cmd
west build -p always -b nucleo_f413zh app-blinky
```