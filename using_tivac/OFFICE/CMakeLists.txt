cmake_minimum_required(VERSION 3.8.2)
project(linux_blinky)

#Toolchain file
include(tm4c123g.cmake)

#Tivaware files $ENV{HOME}/tiva-projects/tivaware
set(TIVAWARE_PATH "/mnt/c/Users/aibar/Downloads/REPOSITORY/project-guild/Embedded-Systems/Training-Camp/using_tivac/tivaware")
include_directories(${TIVAWARE_PATH})

#Source files
file(GLOB SOURCES "src/*.c")
add_executable(${CMAKE_PROJECT_NAME}.axf ${SOURCES})

target_link_libraries(${CMAKE_PROJECT_NAME}.axf 
    ${TIVAWARE_PATH}/usblib/gcc/libusb.a

    ${TIVAWARE_PATH}/driverlib/gcc/libdriver.a
)
