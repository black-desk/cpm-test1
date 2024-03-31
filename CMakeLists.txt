cmake_minimum_required(VERSION 3.29)
project(test)
include(./cmake/CPM.cmake)
add_subdirectory(subdir)
cpmfindpackage(
  NAME
  nlohmann_json
  VERSION
  3.11.2
  URL
  "https://github.com/nlohmann/json/releases/download/v3.11.2/json.tar.xz"
  EXCLUDE_FROM_ALL
  ON)
if(NOT TARGET nlohmann_json::nlohmann_json)
  message(FATAL_ERROR "BUG")
endif()
