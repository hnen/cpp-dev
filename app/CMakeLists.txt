cmake_minimum_required (VERSION 2.8.11)

if(MSVC)
    set(LIBS ${LIBS} ${CMAKE_PREFIX_PATH}/lib/glfw3.lib)
else()
    set(LIBS ${LIBS} ${CMAKE_PREFIX_PATH}/lib/glfw3)
endif()

add_executable (app src/test.cpp)
target_link_libraries (app LINK_PUBLIC ${LIBS})

if(APPLE)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AppKit -framework IOKit -framework CoreVideo")
endif()
