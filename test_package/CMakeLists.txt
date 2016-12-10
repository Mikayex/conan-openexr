PROJECT(PackageTest)
cmake_minimum_required(VERSION 2.8)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
CONAN_BASIC_SETUP()

IF (WIN32)
    ADD_DEFINITIONS(-DOPENEXR_DLL)
ENDIF ()

ADD_EXECUTABLE(testPackage main.cpp drawImage.cpp previewImageExamples.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CONAN_INCLUDE_DIRS})
TARGET_LINK_LIBRARIES(testPackage ${CONAN_LIBS})

