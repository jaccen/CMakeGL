cmake_minimum_required(VERSION 3.14)
project(runtime)

add_subdirectory(lib)

set(sourceFiles
    Application.cpp
)

add_library(runtime ${sourceFiles})

find_package(OpenGL REQUIRED)

target_include_directories(runtime PUBLIC include)

target_link_libraries(runtime PRIVATE glfw glad glm TracyClient spdlog imgui)
