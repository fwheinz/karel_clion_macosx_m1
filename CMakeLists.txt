cmake_minimum_required(VERSION 3.6)
project(StarterProject)

set(CMAKE_C_STANDARD 11)

set(SOURCE_FILES HelloKarel.c)

# Include Directories
include_directories("include" "/usr/local/include" "/opt/homebrew/include")
link_directories("/usr/local/lib" "/opt/homebrew/lib/")

# Executables
add_executable(StarterProject ${SOURCE_FILES})

# Linked Libraries

target_link_libraries(StarterProject ${CMAKE_CURRENT_SOURCE_DIR}/lib/libkarel.a)
target_link_libraries(StarterProject SDLmain)
target_link_libraries(StarterProject SDL)
target_link_libraries(StarterProject SDL_image)
target_link_libraries(StarterProject SDL_ttf)
target_link_libraries(StarterProject pthread)

target_link_options(StarterProject PUBLIC -framework Cocoa)

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/assets DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/data DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
