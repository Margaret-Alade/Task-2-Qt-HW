cmake_minimum_required(VERSION 3.16)

project(Task-2-Qt LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Core)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Core)
find_package(Qt6 REQUIRED COMPONENTS Sql)
find_package(Qt6 REQUIRED COMPONENTS Network)

add_executable(Task-2-Qt
  main.cpp
)
target_link_libraries(Task-2-Qt Qt${QT_VERSION_MAJOR}::Core)
target_link_libraries(Task-2-Qt Qt6::Sql)
target_link_libraries(Task-2-Qt Qt6::Network)

include(GNUInstallDirs)
install(TARGETS Task-2-Qt
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
