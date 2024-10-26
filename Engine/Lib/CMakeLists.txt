set(CMAKE_CXX_STANDARD 17)

include(FetchContent)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 2.6.x
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

add_library(3d_Engine SHARED
    Include/Window/Window.hpp
    Source/Window.cpp
)

set_target_properties(3d_Engine PROPERTIES LINKER_LANGUAGE CXX)

target_include_directories(3d_Engine
    PRIVATE
        Include
        Source
)

target_link_libraries(3d_Engine
    PRIVATE 
        sfml-graphics
)

add_library(3dEngine ALIAS 3d_Engine)