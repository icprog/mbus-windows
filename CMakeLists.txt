cmake_minimum_required(VERSION 2.8)
project(mbus-windows)

include_directories(../)

add_library(mbus SHARED mbus.c mbus-protocol.c mbus-protocol-aux.c mbus-serial-windows.c)

add_executable(mbus-serial-request-data mbus-serial-request-data.c)
target_link_libraries(mbus-serial-request-data mbus)

add_executable(mbus-serial-scan-secondary mbus-serial-scan-secondary.c)
target_link_libraries(mbus-serial-scan-secondary mbus)

add_executable(mbus-serial-scan mbus-serial-scan.c)
target_link_libraries(mbus-serial-scan mbus)

add_executable(mbus-serial-select-secondary mbus-serial-select-secondary.c)
target_link_libraries(mbus-serial-select-secondary mbus)