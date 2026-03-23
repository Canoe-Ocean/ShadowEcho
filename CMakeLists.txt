cmake_minimum_required(VERSION 3.10)
project(ShadowEcho)

set(CMAKE_CXX_STANDARD 17)

# 1. 包含头文件目录
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 2. 【关键修改】使用绝对路径扫描 src 目录
file(GLOB SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp")

# 3. 打印一下找到的文件列表（方便调试，如果还是报错，你可以看到底找没找到文件）
message(STATUS "找到的源文件列表: ${SOURCES}")

# 4. 检查是否找到了源文件
if(NOT SOURCES)
    message(FATAL_ERROR "在 ${CMAKE_CURRENT_SOURCE_DIR}/src 目录下没有找到任何 .cpp 文件！")
endif()

# 5. 创建可执行文件
add_executable(shadow_echo ${SOURCES})

# 6. 链接库
target_link_libraries(shadow_echo raylib GL m pthread dl rt X11)