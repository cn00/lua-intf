cmake_minimum_required(VERSION 3.13)
include("../cmake/source_group_by_dir.cmake")

project(LuaIntf)

# add_subdirectory(third_party/flatbuffers)
# add_subdirectory(third_party/lua)

# file(GLOB_RECURSE sources ./LuaIntf/src/*.cpp ./LuaIntf/src/*.c ./LuaIntf/*.h ./LuaIntf/src/*.h  ./LuaIntf/impl/*.h)
file(GLOB_RECURSE LuaIntf_sources ./LuaIntf/*.h ./LuaIntf/impl/*.h)

# set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -x c++")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -stdlib=libc++ ")
set(LUAINTF_HEADERS_ONLY OFF)

include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/LuaIntf
  ${CMAKE_CURRENT_SOURCE_DIR}/LuaIntf/impl
  ${CMAKE_CURRENT_SOURCE_DIR}/../lua
)
source_group_by_dir(${CMAKE_CURRENT_SOURCE_DIR} LuaIntf_sources)

# link_directories(
#     ${CMAKE_SOURCE_DIR}/lib
# )

# add_library(LuaIntf STATIC ${sources})



