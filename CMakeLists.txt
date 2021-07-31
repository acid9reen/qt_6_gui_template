cmake_minimum_required(VERSION 3.18)
project(qt_charts_demo)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(QT_VERSION 6)
set(REQUIRED_LIBS Core Gui Widgets #[[Charts]])
set(REQUIRED_LIBS_QUALIFIED Qt6::Core Qt6::Gui Qt6::Widgets #[[Qt6::Charts]]) 

find_package(Qt${QT_VERSION} COMPONENTS ${REQUIRED_LIBS} REQUIRED)

add_executable(${PROJECT_NAME}
    main_window.ui
    main_window.h 
    main_window.cpp 
    main.cpp)

target_link_libraries(${PROJECT_NAME} ${REQUIRED_LIBS_QUALIFIED})

