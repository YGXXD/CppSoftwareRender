aux_source_directory(. SOURCE_FILES)
aux_source_directory(math/. SOURCE_FILES)
aux_source_directory(render/. SOURCE_FILES)

add_executable(demo01 ${SOURCE_FILES})
set_target_properties(demo01 PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")

find_package(PkgConfig REQUIRED)

pkg_check_modules(SDL2 sdl2 REQUIRED IMPORTED_TARGET)
target_link_libraries(demo01 PRIVATE PkgConfig::SDL2)

pkg_check_modules(SDL2_IMAGE sdl2_image REQUIRED IMPORTED_TARGET)
target_link_libraries(demo01 PRIVATE PkgConfig::SDL2_IMAGE)
