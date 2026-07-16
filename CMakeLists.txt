cmake_minimum_required(VERSION 3.24)

project(gridx_cpp_sdk
    "${CMAKE_CURRENT_SOURCE_DIR}/VERSION"
    LANGUAGES CXX
)

find_package(Protobuf CONFIG REQUIRED)

file(GLOB_RECURSE GRIDX_PROTO_SRCS CONFIGURE_DEPENDS
    "${CMAKE_CURRENT_SOURCE_DIR}/gen/*.pb.cc"
)

file(GLOB_RECURSE GRIDX_PROTO_HDRS CONFIGURE_DEPENDS
    "${CMAKE_CURRENT_SOURCE_DIR}/gen/*.pb.h"
)

add_library(gridx_cpp_sdk STATIC
    ${GRIDX_PROTO_SRCS}
    ${GRIDX_PROTO_HDRS}
)

add_library(gridx::cpp_sdk ALIAS gridx_cpp_sdk)

target_compile_features(gridx_cpp_sdk
    PUBLIC
        cxx_std_20
)

target_include_directories(gridx_cpp_sdk
    PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}/gen"
)

target_link_libraries(gridx_cpp_sdk
    PUBLIC
        protobuf::libprotobuf
)