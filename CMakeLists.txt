cmake_minimum_required(VERSION 3.24)

add_library(thunderbreath SHARED src/init.cpp)
target_link_libraries(thunderbreath PUBLIC ${Dragon_LINK_LIBRARIES})
target_include_directories(thunderbreath PUBLIC ${Dragon_INCLUDE_DIRS})
add_library(Dragon::Thunderbreath ALIAS thunderbreath)