cmake_minimum_required(VERSION 3.11 FATAL_ERROR)
project(triglobe LANGUAGES CXX)

add_executable(triglobe)

set(QT_MIN_VERSION "5.6.3")

find_package(Qt5 ${QT_MIN_VERSION} REQUIRED COMPONENTS
  Core
)

set(GDAL_MIN_VERSION "3.0.0")
find_package(GDAL ${GDAL_MIN_VERSION} REQUIRED)

set(GLM_VERSION "0.9.9")
find_package(glm ${GLM_VERSION} REQUIRED)

set_target_properties(triglobe
  PROPERTIES
    AUTOMOC ON
)

target_sources(triglobe
  PRIVATE
    src/main.cpp
    src/sdfunction.cpp
    src/triangulator.cpp
)

target_include_directories(triglobe
  PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/src
    ${CMAKE_BINARY_DIR}
)

target_compile_features(triglobe
  PRIVATE
    cxx_std_17
)

target_link_libraries(triglobe
  PRIVATE
    GDAL::GDAL
    Qt5::Core
)


install(TARGETS triglobe)

