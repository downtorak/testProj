cmake_minimum_required(VERSION 2.8)

project(TestProject)

add_executable(test main.cpp)

install(TARGETS test DESTINATION TestProject)

set(CPACK_PACKAGE_NAME test)
set(CPACK_PACKAGE_VERSION 1.0.0)
set(CPACK_PACKAGE_FILE_NAME ${CPACK_PACKAGE_NAME}-${CPACK_PACKAGE_VERSION})
set(CPACK_INCLUDE_TOPLEVEL_DIRECTORY FALSE)
set(CPACK_GENERATOR TGZ)
include(CPack)
