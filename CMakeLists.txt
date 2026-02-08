cmake_minimum_required(VERSION 3.21)
project(MinimalBrowser LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)

find_package(Qt6 REQUIRED COMPONENTS Core Gui Widgets)

FetchContent_Declare(
    curl
    GIT_REPOSITORY https://github.com/curl/curl.git
    GIT_TAG curl-8_18_0
)

set(BUILD_CURL_EXE OFF CACHE BOOL "" FORCE)
set(BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)
set(HTTP_ONLY ON CACHE BOOL "" FORCE)
set(CURL_DISABLE_TESTS ON CACHE BOOL "" FORCE)

FetchContent_MakeAvailable(curl)

add_executable(MinimalBrowser
    Source/main.cpp
)

target_link_libraries(MinimalBrowser PRIVATE
    Qt6::Core
    Qt6::Gui
    Qt6::Widgets
    CURL::libcurl
)
