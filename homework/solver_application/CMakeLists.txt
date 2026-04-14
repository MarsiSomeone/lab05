
cmake_minimum_required(VERSION 3.4)
project(solver)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(../formatter_ex ${CMAKE_BINARY_DIR}/formatter_ex)
add_subdirectory(../solver_lib ${CMAKE_BINARY_DIR}/solver_lib)

add_executable(equation ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)

target_include_directories(equation PUBLIC 
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib
    ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex
    ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib
)
target_link_libraries(equation PRIVATE formatter_ex solver)
