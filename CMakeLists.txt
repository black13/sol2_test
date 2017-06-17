cmake_minimum_required (VERSION 3.2)

project (sol2_test)

#version number
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set (CMakeHelloWorld_VERSION_MAJOR 1)
set (CMakeHelloWorld_VERSION_MINOR 0)

#include the subdirectory containing our libs
add_subdirectory (lua-5.3.4)
include_directories(lua-5.3.4/src)
include_directories(include)
#indicate the entry point for the executable
add_executable (sol2_test lua-5.3.4 tests.cpp
                                    test_containers.cpp
				    test_environments.cpp
				    test_overflow.cpp
				    test_strings.cpp
				    test_containers.cpp
				    test_functions.cpp
				    test_simple_usertypes.cpp
				    test_tables.cpp
				    test_coroutines.cpp
				    test_inheritance.cpp
				    test_state.cpp
				    test_usertypes.cpp
				    test_customizations.cpp
				    test_operators.cpp
				    test_storage.cpp
				    )

set_target_properties(sol2_test PROPERTIES
    CXX_STANDARD 14
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)
# Indicate which libraries to include during the link process.
target_link_libraries (sol2_test lua-5.3.4)

install (TARGETS sol2_test DESTINATION bin)
