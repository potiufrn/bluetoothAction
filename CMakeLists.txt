cmake_minimum_required(VERSION 3.10)

# set the project name
project(bluetoothAction)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")

# Cria uma biblioteca compartilhada
add_library(bluetoothAction SHARED bluetoothAction.cpp bluetoothAction.h)
# Cria uma biblioteca estática
# add_library(bluetoothAction STATIC bluetoothAction.cpp bluetoothAction.h)

target_link_libraries(bluetoothAction PUBLIC bluetooth)

install(TARGETS bluetoothAction DESTINATION lib)
install(FILES bluetoothAction.h DESTINATION include)
