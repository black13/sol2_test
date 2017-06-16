cmake_minimum_required(VERSION 2.8.11)

set(EXECUTABLE_OUTPUT_PATH "bin")
#set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "bin")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")
add_subdirectory(lua-5.3.4)
include_directories(${lua_SOURCE_DIR})
add_executable(sol2_test test.cpp)
target_link_libraries(sol2_test lua)
