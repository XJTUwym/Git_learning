cmake_minimum_required(VERSION 3.15)#指定使用的 cmake 的最低版本
project(demo)#定义工程名
find_package(OpenCV 4.5 REQUIRED)#寻找系统库
set(EXECUTABLE_OUTPUT_PATH ../)#指定可执行程序的输出路径
file(GLOB SRC ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)#搜索src下的从cpp源文
include_directories(${OPENCV_INCLUDE_DIRS})#包含头文件
add_executable(app ${SRC} main.cpp)#确定需要编译的源文件和输出的可执行程序名
target_link_libraries(app ${OpenCV_LIBS})#链接系统库

