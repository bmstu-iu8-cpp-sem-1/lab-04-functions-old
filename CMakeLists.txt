cmake_minimum_required (VERSION 2.8)

include(gtest.cmake)

include_directories(SYSTEM
    ./
)

ADD_DEFINITIONS(
    -std=c++11
)

# enum your files
add_executable(executable
  test.cpp 
)

find_package (Threads)
target_link_libraries(executable -fsanitize=address gtest ${CMAKE_THREAD_LIBS_INIT})
