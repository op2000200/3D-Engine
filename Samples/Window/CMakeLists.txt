set(CMAKE_CXX_STANDARD 17)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

include(FetchContent)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 2.6.x
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

add_executable(sampleWindow
    SampleWindow.cpp
)

add_dependencies(sampleWindow 3d_Engine)

target_link_libraries(sampleWindow
    PRIVATE 
        3d_Engine
        sfml-graphics
)