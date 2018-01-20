
set(LIBS ${LIBS} ${CMAKE_PREFIX_PATH}/lib/glfw3)

add_executable (app src/test.cpp)
target_link_libraries (app LINK_PUBLIC ${LIBS})

if(APPLE)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AppKit -framework IOKit -framework CoreVideo")
endif()
