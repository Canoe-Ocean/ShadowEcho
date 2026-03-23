cmake_minimum_required(VERSION 3.10)
project(ShadowEcho)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 17)

# 包含头文件目录
include_directories(include)

# 【修正处】使用 GLOB RECURSIVE 自动扫描所有源文件
file(GLOB_RECURSIVE SOURCES "src/*.cpp")

# 添加可执行文件，包含入口 main.cpp 和所有扫描到的模块
add_executable(shadow_echo main.cpp ${SOURCES})

# 链接 raylib 及其在 Linux 系统下的依赖
target_link_libraries(shadow_echo raylib GL m pthread dl rt X11)