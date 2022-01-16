cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(cmake_and_cuda LANGUAGES CXX CUDA)
include(CTest)

include_directories(${PROJECT_SOURCE_DIR}/ParticlesLibrary)
add_subdirectory(${PROJECT_SOURCE_DIR}/ParticlesLibrary)
link_directories(build/ParticlesLibrary)

enable_testing()
add_subdirectory(${PROJECT_SOURCE_DIR}/TestParticlesLibrary)

add_test(NAME particles_10k COMMAND particle_test 10000 )
add_test(NAME particles_256k COMMAND particle_test 256000 )