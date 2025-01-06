cmake_minimum_required(VERSION 3.29)

set(LIB_NAME imgui)
project(${LIB_NAME})
set(SOURCES imgui.cpp imgui_draw.cpp imgui_tables.cpp imgui_widgets.cpp imgui.h imgui_internal.h)
add_library(${LIB_NAME} ${SOURCES})
target_include_directories(${LIB_NAME} PUBLIC .)
