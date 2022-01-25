cmake_minimum_required(VERSION 3.13)
get_filename_component(ProjectId ${CMAKE_CURRENT_SOURCE_DIR} NAME)
string(REPLACE " " "_" ProjectId ${ProjectId})
project(${ProjectId})
set(CMAKE_CXX_STANDARD 20)
SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${${PROJECT_NAME}_SOURCE_DIR}/bin/${CMAKE_BUILD_TYPE})
set(SDL2_INCLUDE_DIR YOUR_SDL_INCLUDE_DIR) #Insert SDL include diretory here!
set(SDL2_LIB_DIR YOUR_SDL_LIB_DIR) #Insert SDL lib directory here
include_directories(${SDL2_INCLUDE_DIR})
link_directories(${SDL2_LIB_DIR})
file(GLOB SOURCES src/*.cpp)
add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} SDL2main SDL2)