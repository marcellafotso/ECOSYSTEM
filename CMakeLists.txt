cmake_minimum_required(VERSION 3.10)
project(ecosystem_simulator)

set(CMAKE_CXX_STANDARD 17)
include_directories(include)

add_executable(ecosystem
    src/main.cpp
    src/Core/Entity.cpp
    src/Core/Ecosystem.cpp
    src/Graphics/Window.cpp
    src/Graphics/Renderer.cpp
)

find_package(SDL3 REQUIRED)
target_link_libraries(ecosystem SDL3::SDL3)
