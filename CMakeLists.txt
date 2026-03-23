cmake_minimum_required(VERSION 3.10)
project(ShadowEcho)

set(CMAKE_CXX_STANDARD 17)

# 1. 包含头文件目录
include_directories(include)

# 2. 扫描 src 目录下所有的 .cpp 文件 (这会包含 src/main.cpp)
file(GLOB SOURCES "src/*.cpp")

# 3. 检查是否找到了源文件，如果没有找到则报错提示
if(NOT SOURCES)
    message(FATAL_ERROR "在 src 目录下没有找到任何 .cpp 文件！请检查目录结构。")
endif()

# 4. 创建可执行文件，直接使用扫描到的 SOURCES 列表
add_executable(shadow_echo ${SOURCES})

# 5. 链接库
target_link_libraries(shadow_echo raylib GL m pthread dl rt X11)