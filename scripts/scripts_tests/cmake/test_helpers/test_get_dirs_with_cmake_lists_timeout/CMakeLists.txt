cmake_minimum_required(VERSION 3.30)
project(cmake_test_get_subdirectories_with_cmake_lists)

add_subdirectory(custom_targets)

include(${CMAKE_CURRENT_LIST_DIR}/../../../cmake/common.cmake)
include(${CMAKE_SCRIPTS_DIR}/debug.cmake)
include(${CMAKE_SCRIPTS_DIR}/dir_opts.cmake)

get_subdirectories_with_cmake_lists_txt(${CMAKE_CURRENT_LIST_DIR})

print_debug("SUBDIRECTORIES: ${GET_SUBDIRECTORIES_OUTPUT}" "${CMAKE_CURRENT_LIST_FILE}")

if(NOT "${GET_SUBDIRECTORIES_OUTPUT}" MATCHES "hello_world")
    message(FATAL_ERROR "Test failed: ${CMAKE_CURRENT_LIST_DIR}" )
endif()




