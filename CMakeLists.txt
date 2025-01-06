cmake_minimum_required(VERSION 3.29)

set(LIB_NAME imgui)
project(${LIB_NAME})
set(SOURCES imgui.cpp imgui_draw.cpp imgui_tables.cpp imgui_widgets.cpp imgui.h imgui_internal.h)
add_library(${LIB_NAME} ${SOURCES})
target_include_directories(${LIB_NAME} PUBLIC .)

SET(DEMO_NAME "imgui_sdl3_renderer_demo")
SET(DEMO_SOURCES examples/example_sdl3_sdlrenderer3/main.cpp imgui_demo.cpp backends/imgui_impl_sdl3.h backends/imgui_impl_sdl3.cpp backends/imgui_impl_sdlrenderer3.h backends/imgui_impl_sdlrenderer3.cpp)
add_executable(${DEMO_NAME} ${DEMO_SOURCES})
target_include_directories(${DEMO_NAME} PRIVATE backends)
target_link_libraries(${DEMO_NAME} PRIVATE SDL3::SDL3 imgui)
