# CMake Example
---
title: CMake Example
author: Fengyi Liu
date: 2024-12-24
---
Github: https://github.com/lucasliu2019/cmake
We create some simple examples for CMake. CMake helps automate the compilation process!


## Requirement
Required tools:
- CMake (to create makefile and import library)
- VSCode (optional)

Required library:
- wxWidgets (for GUIs)

### Installation and setup of Raylib
For Linux, we use the brew command to install cmake. 
```
brew install cmake
```


### Installation and setup of VSCode
For VSCode, we will install the extension called CMake Tools. This extension will help use to comiple the source code using CMake according to the setups in "CMakeLists.txt".


## How to compile
Note that VSCode is optional, you could directly use CMake. To use VSCode, we first open the folder of the project, the file organization is shown in the next Section "File Structure". Once the folder is open in VSCode, click the CMake extension. Next, we click "Delete Cache and Reconfiguration" icon beside the "PROJECT STSTUS" tab. Once it is successfully built, we can run/compile our project in the "PROJECT OUTLINE" tab. Find the executable 'myGame' and right-click to run/debug. 

We can change the compiled project name by changing 'test' to the desired project name in the 2nd line in CMakeLists.txt
```
project(test)
```

## File structure
The structure of the files is organized in the following way:
```
project
│   README.md
│   CMakeLists.txt    
│
└───src
│   │   main.cpp
│   │   ...
│   
└───build (genered by CMake)
    │   ...
    │
```

There is no build foler initially, and it is generated by CMake. The executable file is located in the build folder in the project folder.


### version
The following line tells us the minimum version of CMake required to run the CMake.
```
cmake_minimum_required(VERSION 3.10.0)
```

### variable
The following line defines the name of the project as "test"
```
project(test)
```
To use the variable, we use the following syntax
```
${varNaprojectme}
```
In the above line, it will substitute ${project} with the assigned value (test) to the project.

## Executable
```
add_executable(${PROJECT_NAME} ./src/main.cpp)
```
The above command tells us where to find the source file and its name ( ./src/main.cpp) and the name of the compiled file name (${PROJECT_NAME}) will be created in build folder.
