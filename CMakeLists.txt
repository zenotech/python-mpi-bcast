cmake_minimum_required(VERSION 3.8)

project(python-mpi-bcast)

find_package(libarchive REQUIRED)

set(SRC bcast.c bcast-tar.c)

add_executable(bcast ${SRC})
target_include_directories(bcast ${LibArchive_INCLUDE_DIRS})
target_link_libraries(bcast ${LibArchive_LIBRARIES})

install(FILES bcast DESTINATION bin)
install(FILES activate.sh DESTINATION bin)