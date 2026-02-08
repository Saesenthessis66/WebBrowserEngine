# WebBrowserEngine

A minimal cross-platform C++ web browser engine built with Qt and
libcurl.

## Overview

WebBrowserEngine is a lightweight experimental browser engine written in
modern C++.\
It uses:

-   **Qt 6** for GUI and application framework
-   **libcurl** for HTTP networking
-   **CMake** for cross-platform builds

The project builds on both Windows and Linux.

------------------------------------------------------------------------

## Requirements

-   CMake 3.16 or newer
-   C++17 compatible compiler
-   Qt 6
-   libcurl
-   OpenSSL development libraries

------------------------------------------------------------------------

The executable will be generated inside the `build` directory.

# Building on Windows (MinGW)

## 1. Install Qt

Add the following directories to your system `Path` environment
variable:

    C:\Qt\6.x.x\mingw_64\bin
    C:\Qt\Tools\mingwxxxx\bin

## 3. Build the Project

    cmake -S . -B build -G "MinGW Makefiles"
    cmake --build build

------------------------------------------------------------------------

# Building on Linux (Ubuntu / Debian)

## 1. Install Dependencies

    sudo apt update
    sudo apt install qt6-base-dev qt6-tools-dev cmake g++
    sudo apt install libssl-dev

## 2. Build the Project

    cmake -S . -B build
    cmake --build build

------------------------------------------------------------------------
