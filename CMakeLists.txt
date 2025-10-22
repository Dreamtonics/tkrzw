cmake_minimum_required(VERSION 3.21)
project(tkrzw)

if(${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_BINARY_DIR})
  message(FATAL_ERROR
    "In-source builds are not allowed."
    "\n Please remove \"${CMAKE_SOURCE_DIR}/CMakeCache.txt\" and try again from another folder"
  )
endif()

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# The static library: libciglet.a
add_library(tkrzw STATIC
  tkrzw_compress.cc
  tkrzw_dbm.cc
  tkrzw_dbm_async.cc
  tkrzw_dbm_baby.cc
  tkrzw_dbm_cache.cc
  tkrzw_dbm_common_impl.cc
  tkrzw_dbm_hash.cc
  tkrzw_dbm_hash_impl.cc
  tkrzw_dbm_poly.cc
  tkrzw_dbm_shard.cc
  tkrzw_dbm_skip.cc
  tkrzw_dbm_skip_impl.cc
  tkrzw_dbm_std.cc
  tkrzw_dbm_tiny.cc
  tkrzw_dbm_tree.cc
  tkrzw_dbm_tree_impl.cc
  tkrzw_dbm_ulog.cc
  tkrzw_file_mmap.cc
  tkrzw_file_poly.cc
  tkrzw_file_pos.cc
  tkrzw_file_std.cc
  tkrzw_file_util.cc
  tkrzw_hash_util.cc
  tkrzw_lib_common.cc
  tkrzw_message_queue.cc
  tkrzw_str_util.cc
  tkrzw_time_util.cc

  tkrzw_compress.h
  tkrzw_dbm.h
  tkrzw_dbm_async.h
  tkrzw_dbm_baby.h
  tkrzw_dbm_cache.h
  tkrzw_dbm_common_impl.h
  tkrzw_dbm_hash.h
  tkrzw_dbm_hash_impl.h
  tkrzw_dbm_poly.h
  tkrzw_dbm_shard.h
  tkrzw_dbm_skip.h
  tkrzw_dbm_skip_impl.h
  tkrzw_dbm_std.h
  tkrzw_dbm_tiny.h
  tkrzw_dbm_tree.h
  tkrzw_dbm_tree_impl.h
  tkrzw_dbm_ulog.h
  tkrzw_file_mmap.h
  tkrzw_file_poly.h
  tkrzw_file_pos.h
  tkrzw_file_std.h
  tkrzw_file_util.h
  tkrzw_hash_util.h
  tkrzw_lib_common.h
  tkrzw_message_queue.h
  tkrzw_str_util.h
  tkrzw_time_util.h
)

target_compile_definitions(tkrzw PRIVATE _TKRZW_PKG_VERSION="1.0.32" _TKRZW_LIB_VERSION="1.75.0")

install(TARGETS tkrzw
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION bin
)
