cmake_minimum_required(VERSION 3.15)#指定使用的 cmake 的最低版本
project(demo)#定义工程名
find_package(OpenCV 4.5 REQUIRED)#寻找系统库
#message打印变量
message(STATUS "OpenCV_DIR = ${OpenCV_DIR}")
message(STATUS "OpenCV_INCLUDE_DIRS = ${OpenCV_INCLUDE_DIRS}")
message(STATUS "OpenCV_LIBS = ${OpenCV_LIBS}")



file(GLOB SRC ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)#搜索src下的从cpp源文件

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include ${OPENCV_INCLUDE_DIRS})#包含include下的头文件

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)#包含库文件(私人库需要这个)

add_executable(app ${SRC} main.cpp)#确定需要编译的源文件和输出的可执行程序名

 
target_link_libraries(app ${OpenCV_LIBS})#链接系统库
#这是一段更改