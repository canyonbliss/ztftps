# Copyright (c) 2025 Canyon Bliss
# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)

project(ztftps LANGUAGES CXX)

if(CONFIG_LIB_ZTFTPS)
    add_library(ztftps INTERFACE)
    zephyr_include_directories(${ZEPHYR_CURRENT_MODULE_DIR}/lib)
    zephyr_library()
    add_subdirectory(lib)
    zephyr_library_link_libraries(ztftps)
    target_link_libraries(ztftps INTERFACE zephyr_interface)
endif(CONFIG_LIB_ZTFTPS)
