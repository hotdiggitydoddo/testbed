CMAKE_MINIMUM_REQUIRED(VERSION 3.13)

project(glad)
include_directories(include)
add_library(glad src/glad.c)