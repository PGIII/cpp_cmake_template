#FIXME: rename program name to whatever you want
# add our exe, as well as enable warnings
add_executable(program_name main.cpp)
target_include_directories(program_name PRIVATE ${CMAKE_CURRENT_LIST_DIR})
# Set clang tidy here so we dont run it on Unit tests, since catch has a lot of
# warnings from clang-tidy
set_target_properties(program_name PROPERTIES CXX_CLANG_TIDY clang-tidy)
# NOTE: in a more complicated project warnings should be in a toolchain file
# specified by the preset
target_compile_options(program_name PRIVATE -Wall -Wextra)

