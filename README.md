# Libwebsocket ESP32 component

This is a Espressif ESP-IDF CMake Build System component wrapper for Libwebsocket library. 

If you are not using ESP-IDF and its CMake Build System, please ignore this wrapper and try using Libwebsocket directly.

## Demo project (WIP)

https://github.com/huming2207/lws-esp32-test

## Usage

1. Enter the 'esp-idf' directory
2. Run `git submodule add https://github.com/FredrikFornstad/lws-esp32.git components/lws-esp32`
3. Run `git submodule update --init --recursive`
4. Go to 'your_project'/main directory and open the `CMakeList.txt`, add `REQUIRES lws-esp32` into `idf_component_register()` function
5. Reload the project (if you are using IDE or editor plugin)

## TODO

1. Better documentation & demo project?
2. Make a bot for dynamically update the Libwebsocket submodule?