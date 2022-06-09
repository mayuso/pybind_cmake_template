cmake_minimum_required(VERSION 3.16)
project(pybind_cmake_template)

add_subdirectory(vendor/pybind11)
pybind11_add_module(${PROJECT_NAME} src/main.cpp)

# EXAMPLE_VERSION_INFO is defined by setup.py and passed into the C++ code as a
# define (VERSION_INFO) here.
target_compile_definitions(${PROJECT_NAME}
                           PRIVATE VERSION_INFO=${EXAMPLE_VERSION_INFO})
