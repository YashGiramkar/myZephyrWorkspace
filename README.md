# myZephyrWorkspace

Zephyr RTOS workspace using **forest topology** with a **freestanding manifest repository**.

## Zephyr version
- Zephyr: 3.7 LTS
- SDK: 0.16.8

## Board Tested For
- STM32F413ZH
- Nucleo-F413ZH

## Setup for Windows users
First craete a myZephyrWorkspace directory
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

Post running the above mentioned command you should see the following repository structure:

```cmd
west-workspace/
├── app1/               # .git/ project
│   ├── CMakeLists.txt
│   ├── prj.conf
│   └── src/
│       └── main.c
├── app2/               # .git/ project
│   ├── CMakeLists.txt
│   ├── prj.conf
│   └── src/
│       └── main.c
├── manifest-repo/      # .git/ never modified by west
│   └── west.yml        # main manifest with optional import(s) and override(s)
├── modules/
│   └── lib/
│       └── zcbor/      # .git/ project from either the main manifest or
│                       #       from some import
│
└── zephyr/             # .git/ project
    └── west.yml        # This can be partially imported with lower precedence or ignored.
                        # Only the 'manifest-rev' version can be imported.
```

## Attach the deattached applciations head
At this point applications would also have been checcked out, but the applications would be head detached state.
So before proceeding any further, we can just re-attach the head with following command.
For sample repository app-blinky the comamnd goes as follows:
```cmd
cd app-blinky
git pull --rebase origin main
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