cmake_minimum_required(VERSION 3.16)
project(qt5integration VERSION 1.0 LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

# Set up AUTOMOC and some sensible defaults for runtime execution
# When using Qt 6.3, you can replace the code block below with
# qt_standard_project_setup()
set(CMAKE_AUTOMOC ON)
include(GNUInstallDirs)

find_package(QT NAMES Qt5 Qt6 REQUIRED COMPONENTS Core)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Concurrent DBus Gui Widgets X11Extras)
find_package(Qt${QT_VERSION_MAJOR} OPTIONAL_COMPONENTS ThemeSupport)


add_subdirectory(styleplugins)
add_subdirectory(platformthemeplugin)
add_subdirectory(iconengineplugins)
add_subdirectory(imageformatplugins)
add_subdirectory(tests)
if(NOT BASED_DTK_DIR_ISEMPTY)
    add_subdirectory(src)
endif()
if(CMAKE_BUILD_TYPE STREQUAL Debug)
    add_subdirectory(styles)
endif()
