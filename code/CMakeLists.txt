cmake_minimum_required(VERSION 3.16)
project(cshep VERSION 0.1.0)

find_package(TBB REQUIRED)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

string(APPEND CMAKE_CXX_FLAGS " -Wall -Wextra")

string(APPEND CMAKE_CXX_FLAGS_DEBUG
       " -fsanitize=address -fno-omit-frame-pointer")
string(APPEND CMAKE_EXE_LINKER_FLAGS_DEBUG
       " -fsanitize=address -fno-omit-frame-pointer")

add_executable(algo algo.cpp)
add_executable(algo_solution algo_solution.cpp)

add_executable(algo_functions algo_functions.cpp)
add_executable(algo_functions_solution algo_functions_solution.cpp)
