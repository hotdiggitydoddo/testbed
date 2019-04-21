CMAKE_MINIMUM_REQUIRED(VERSION 3.13)
set(CMAKE_CXX_STANDARD 14)

project(testgame)

include_directories(../vendor/glad/include)
include_directories(../vendor/glfw/include)

add_definitions(-DGLFW_INCLUDE_NONE)

add_executable(testgame src/Main.cpp)

target_link_libraries(testgame glfw glad ${GLFW_LIBRARIES})



if(MSVC)
    #add_definitions(-DGA_PLATFORM_WINDOWS -DGA_BUILD_DLL)
    target_link_libraries(testgame "opengl32.lib")
endif()
if (APPLE)
    target_link_libraries(testgame "-framework OpenGL")
endif()