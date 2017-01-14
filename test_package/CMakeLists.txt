PROJECT(PackageTest)
cmake_minimum_required(VERSION 2.8)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
CONAN_BASIC_SETUP()

find_package(OpenEXR REQUIRED)

ADD_EXECUTABLE(testPackage main.cpp drawImage.cpp previewImageExamples.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${OPENEXR_INCLUDE_DIRS})
link_directories(${OPENEXR_LIBRARY_DIRS})
TARGET_LINK_LIBRARIES(testPackage ${OPENEXR_LIBRARIES})
