cmake_minimum_required(VERSION 3.20)

set(CXX_FILES src/init.cpp)

if(DRAGON_BUILD_SHARED)
	add_library(thunderbreath SHARED ${CXX_FILES})
else() 
	add_library(thunderbreath STATIC ${CXX_FILES})
endif()
target_include_directories(thunderbreath PUBLIC ${Dragon_INCLUDE_DIRS})
target_link_libraries(thunderbreath ${DRAGON_BUILD_TYPE} ${Boost_LIBRARIES} ${OpenCL_LIBRARIES})
add_library(Dragon::Thunderbreath ALIAS thunderbreath)