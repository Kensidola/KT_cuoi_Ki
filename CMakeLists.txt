cmake_minimum_required (VERSION 3.0)

PROJECT(BT_cuoi_Ki)

set (CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:/Users/datch/OneDrive/Máy tính/Cpp_Thi/opencv/build/x64/vc16/lib")

set(CMAKE_PREFIX_PATH "C:/Users/datch/OneDrive/Máy tính/Cpp_Thi/opencv/build/x64/vc16/lib")

IF(EXISTS ${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup()
ENDIF()

# Requires OpenCV
FIND_PACKAGE( OpenCV 4.0.0 REQUIRED )
MESSAGE("OpenCV version : ${OpenCV_VERSION}")

include_directories("C:/Users/datch/OneDrive/Máy tính/Cpp_Thi/opencv/build/include")
include_directories(${OpenCV_INCLUDE_DIRS})
link_directories("C:/Users/datch/OneDrive/Máy tính/Cpp_Thi/opencv/build/x64/vc16/lib")
link_directories(${OpenCV_LIB_DIR})

ADD_EXECUTABLE( ${PROJECT_NAME} main.cpp utils/MultipleImageWindow.cpp)
TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS} )
