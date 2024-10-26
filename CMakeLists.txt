cmake_minimum_required(VERSION 3.30)

project (3dEngine LANGUAGES CXX)

add_subdirectory(Engine/Lib)

option(BuildExamples "Build examples" ON)

if (${BuildExamples})
    message(STATUS "Enabled building of examples")
    add_subdirectory(Samples/Window)
else ()
    message(STATUS "Disabled building of examples")
endif ()