cmake_minimum_required(VERSION 3.20.0)
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(ssd1315_display)

target_sources(app PRIVATE
    src/main.c
    src/draw.c
    drivers/ssd1315/ssd1315.c
    drivers/ssd1315/ssd1315_reg.c
    drivers/ssd1315/i2c_helper.c


    ../i2c_scanner/src/i2c_scanner.c
)

# Füge den neuen include-Pfad hinzu
target_include_directories(app PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}/include/ssd1315

    ${CMAKE_CURRENT_SOURCE_DIR}/../i2c_scanner/include
)