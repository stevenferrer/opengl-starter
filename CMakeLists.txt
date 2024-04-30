cmake_minimum_required(VERSION 3.28)
include(FetchContent)

project(
    myapp
    VERSION 0.1.0
    LANGUAGES CXX C
)

set(CMAKE_CXX_COMPILER clang++)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
add_compile_options(-Werror)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(VENDOR_DIR "${CMAKE_CURRENT_SOURCE_DIR}/vendor")
set(SRC_DIR "${CMAKE_CURRENT_SOURCE_DIR}/src")

# glfw
FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw.git
    GIT_TAG 3.4
    GIT_SHALLOW ON
)
FetchContent_MakeAvailable(glfw)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

# glad
set(GLAD_DIR ${VENDOR_DIR}/glad)
add_library(glad ${GLAD_DIR}/src/glad.c)
target_include_directories(glad PUBLIC ${GLAD_DIR}/include)

add_executable(${PROJECT_NAME})
target_sources(${PROJECT_NAME}
    PRIVATE
    ${SRC_DIR}/main.cpp
)
target_link_libraries(${PROJECT_NAME}
    PRIVATE
    glfw
    glad
    ${CMAKE_DL_LIBS} # Refer to https://stackoverflow.com/a/56842079/2394163
)
