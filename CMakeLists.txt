cmake_minimum_required(VERSION 3.10)
project(ShadowEcho)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 17)

# 包含头文件目录 (你的 include 文件夹)
include_directories(include)

# 自动扫描 src 目录下所有的 .cpp 文件
file(GLOB_RECURSIVE SOURCES "src/*.cpp")

# 添加可执行文件 (包含 main.cpp 和所有模块)
add_executable(shadow_echo main.cpp ${SOURCES})

# 链接 raylib 及其在 Linux 下的依赖库
target_link_libraries(shadow_echo raylib GL m pthread dl rt X11)