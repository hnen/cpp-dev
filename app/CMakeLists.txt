

link_directories(${CMAKE_SOURCE_DIR}/cget/lib)
include_directories(${CMAKE_SOURCE_DIR}/cget/include)

add_executable (app src/test.cpp)
#link_directories(${PROJECT_SOURCE_DIR}/cget/lib)
target_link_libraries (app LINK_PUBLIC glfw3)

if(APPLE)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AppKit -framework IOKit -framework CoreVideo")
endif()
