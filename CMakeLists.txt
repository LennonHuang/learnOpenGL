cmake_minimum_required(VERSION 3.14)

project(learnOpenGL)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(PROJECT_SOURCES
    glad/glad.h
    KHR/khrplatform.h
    main.cpp
)

set(SOURCE_FILES main.cpp glad.c)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(QT NAMES Qt6 Qt5 COMPONENTS Core REQUIRED)
find_package(Qt${QT_VERSION_MAJOR} COMPONENTS Core REQUIRED)
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)


add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} Qt${QT_VERSION_MAJOR}::Core OpenGL::GL glfw ${CMAKE_DL_LIBS})
