set(TARGET common)

# json.hpp library from: https://github.com/nlohmann/json

add_library(${TARGET} OBJECT common.cpp common.h stb_image.h stb_image_write.h json.hpp)

target_include_directories(${TARGET} PUBLIC .)
target_link_libraries(${TARGET} PRIVATE stable-diffusion ${CMAKE_THREAD_LIBS_INIT})
target_compile_features(${TARGET} PUBLIC cxx_std_11)

# ZIP Library from: https://github.com/kuba--/zip

set(Z_TARGET zip)
add_library(${Z_TARGET} OBJECT zip.c zip.h miniz.h)
target_include_directories(${Z_TARGET} PUBLIC .)