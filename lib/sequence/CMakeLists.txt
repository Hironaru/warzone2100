cmake_minimum_required (VERSION 3.5)
project (sequence CXX)

file(GLOB HEADERS "*.h")
file(GLOB SRC "*.cpp")

find_package(OpenAL REQUIRED)

add_library(sequence ${HEADERS} ${SRC})
target_compile_definitions(sequence PRIVATE "AL_LIBTYPE_STATIC")
target_include_directories(sequence PRIVATE "${OPENAL_INCLUDE_DIR}" ivis-opengl)
target_link_libraries(sequence PRIVATE framework)
