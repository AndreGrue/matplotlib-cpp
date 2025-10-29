cmake_minimum_required(VERSION 3.15)
project(matplotlib-cpp)

find_package(Eigen3 REQUIRED)
find_package(Python3 COMPONENTS Interpreter Development REQUIRED)
find_package(Python3 COMPONENTS NumPy REQUIRED)

message(STATUS "Python3_FOUND:              ${Python3_FOUND}")
message(STATUS "Python3_VERSION:            ${Python3_VERSION}")
message(STATUS "Python3_INCLUDE_DIRS:       ${Python3_INCLUDE_DIRS}")
message(STATUS "Python3_LIBRARIES:          ${Python3_LIBRARIES}")
message(STATUS "Python3_NumPy_FOUND:        ${Python3_NumPy_FOUND}")
message(STATUS "Python3_NumPy_VERSION:      ${Python3_NumPy_VERSION}")
message(STATUS "Python3_NumPy_INCLUDE_DIRS: ${Python3_NumPy_INCLUDE_DIRS}")
message(STATUS "Python3_NumPy_LIBRARIES:    ${Python3_NumPy_LIBRARIES}")

include_directories(
    ${Python3_INCLUDE_DIRS}
    ${Python3_NumPy_INCLUDE_DIRS}
)
link_libraries(
    Eigen3::Eigen
    Python3::Python
    Python3::NumPy
)

add_subdirectory(examples)
