cmake_minimum_required(VERSION 3.5 FATAL_ERROR)
project(inline-namespace-repro)

add_library(reproduction SHARED
  Reproduction.cc
)

add_executable(${PROJECT_NAME} main.cc)

target_link_libraries(
  ${PROJECT_NAME}
  reproduction
)
