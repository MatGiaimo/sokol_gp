cmake_minimum_required(VERSION 3.10)

# Create a library target for sokol_gp
add_library(sokol_gp INTERFACE)

# Add the include directory
target_include_directories(sokol_gp INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}
)

# Add dependencies
# Note: sokol and nuklear are header-only libraries (implementations in sokol_impl.c)
# Only link to actual libraries that exist
target_link_libraries(sokol_gp INTERFACE
    cglm
)

# Implementation macros are handled in sokol_impl.c only
# Do not define SOKOL_IMPL, SOKOL_GP_IMPL, or NK_IMPLEMENTATION here 