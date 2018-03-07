cmake_minimum_required(VERSION 3.8)

project(python-mpi-bcast)

find_package(LibArchive REQUIRED)

find_package(MPI REQUIRED)

set(SRC bcast.c bcast-tar.c)

add_executable(bcast ${SRC})
target_include_directories(bcast PUBLIC ${LibArchive_INCLUDE_DIRS} ${MPI_C_INCLUDE_PATH})
target_link_libraries(bcast PRIVATE ${LibArchive_LIBRARIES} ${MPI_C_LIBRARIES})

install(PROGRAMS ${CMAKE_BINARY_DIR}/bcast DESTINATION bin)
install(FILES activate.sh DESTINATION bin)