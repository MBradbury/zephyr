# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)

if(BOARD STREQUAL qemu_x86_64)
	LIST(APPEND QEMU_EXTRA_FLAGS -machine q35)
endif()

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(smbus)

target_sources(app PRIVATE src/main.c)
