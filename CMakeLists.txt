cmake_minimum_required(VERSION 3.5)
project(rgbdSLAM)

set(CMAKE_CXX_STANDARD 14)

#设定可执行二进制文件的目录
set( EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

#设定存放编译出来的库文件的目录
set( LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
#并且把该目录设为连接目录
link_directories( ${PROJECT_SOURCE_DIR}/lib)

#设定头文件目录
include_directories( ${PROJECT_SOURCE_DIR}/include)

#增加子文件夹，也就是进入源代码文件夹继续构建
add_subdirectory( ${PROJECT_SOURCE_DIR}/src)

