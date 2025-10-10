cmake_minimum_required(VERSION 3.10)
project(DungeonCrawler LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(nlohmann_json CONFIG REQUIRED)
find_package(doctest CONFIG REQUIRED)
find_package(Boost CONFIG REQUIRED COMPONENTS format)
find_package(raylib CONFIG REQUIRED)

add_subdirectory(game)
add_subdirectory(editor)
add_subdirectory(tests)
