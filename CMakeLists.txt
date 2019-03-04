CMAKE_MINIMUM_REQUIRED(VERSION 2.8.7)

SET(CMAKE_INCLUDE_CURRENT_DIR 1)
SET(CMAKE_CXX_STANDARD 11)

SET(SERD_INCL_DIR C:/code/rdf/serd/include)
SET(SERD_LIB_PATH C:/code/rdf/serd/lib/serd.lib)

SET(INCLUDES ${SERD_INCL_DIR} ${PROJECT_SOURCE_DIR}/libhdt/src/util)

add_compile_definitions(_CRT_SECURE_NO_WARNINGS)

add_subdirectory(libcds)
add_subdirectory(libhdt)