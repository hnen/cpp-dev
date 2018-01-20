cmake_minimum_required (VERSION 2.8.11)

# This is needed if not building with 'cget build'
include(${CMAKE_SOURCE_DIR}/cget/cget/cget.cmake)

link_directories(${CMAKE_PREFIX_PATH}/lib)
set(LIBS ${LIBS} glfw3)

add_executable (app src/test.cpp)
target_link_libraries (app LINK_PUBLIC ${LIBS})

if(APPLE)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AppKit -framework IOKit -framework CoreVideo")
endif()

