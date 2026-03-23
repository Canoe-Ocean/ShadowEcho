cmake_minimum_required(VERSION 3.10)
project(ShadowEcho)

set(CMAKE_CXX_STANDARD 17)

# 包含头文件
include_directories(include)

# 扫描 src 目录下所有的 .cpp 文件
file(GLOB SOURCES "src/*.cpp")

# 【修正处】指明 main.cpp 在 src 目录下
add_executable(shadow_echo ${SOURCES})

# 链接库
target_link_libraries(shadow_echo raylib GL m pthread dl rt X11)